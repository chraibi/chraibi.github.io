---
layout: post
title:  "Writing documentation code from markdown files"
image: '/assets/img/totoro.png'
date:   2016-11-16 21:14:00
tags:
- JuPedSim, Pedestrian Dynamics
description: 'JuPedSim Guide'
categories:
- JuPedSim
twitter_text: "Writing documentation code from markdown files"
serie: learn
---

For the documentation of  [JuPedSim](http://jupedsim.org) we decided to go with a `markdown`-based approach, 
where every single article is written in markdown and published using Jekyll on GitHub-Pages. 
Very simple approach that allows focusing on writing the docs without any technical distraction. 

However, surprisingly, using the same `markdown` files to  produce a printable pdf file for the documentation is not
as straightforward as it sounds. In this [article](http://peterlu.github.io/2014/08/03/markdown_latex_pdf.html)
Peter J. Lu gave a nice summary what possibilities there are to convert markdown to pdf file and why there are 
a bunch of problems that you face when you do so.

The solution that he uses delivers the "best" possible result, but still requires some **manual** cleanup of the files. 

Here are the steps: 

- With `Kramdown` convert the markdown file to latex.

  ```python
  kramdown _posts/file.md --no-auto-ids --output latex > file.tex
  ```

- Cleanup `file.tex` by removing  the YAML headers
- Fix the image paths:  replace liquid tags like `site.baseurl` by the an absolute path.

This  python script automates the above mentioned steps

```python
#======================================
# convert _posts/*.md to _tex/*.tex   #
# mkdir _tex/ if it does not exit.    #
#======================================
import glob
import os
import re
import shlex
import subprocess

def clean_file(filename):
    """
    Remove yaml header and fix path to images (remove {{ site.baseurl }})
    """

    f =  open(filename, "r")
    lines = f.readlines()
    if not len(lines):
        print "WARNING: can not read file ", filename
        raw_input("pause")
        
    add_line = 0  # condition when to start adding new lines
    newlines = [] # new lines will be written in filename

    for line in lines:
        # look for first appearance of "---"
        if not add_line and line.startswith("---"):
            add_line = 1
            continue # ignore this line

        if add_line:
            # fix image urls. Replace "{{ base.url }}" with pwd.
            line = re.sub(r"\{\{\s* site.baseurl \s*\}\}", os.getcwd(), line)
            newlines.append(line)

    
    # write new content in file
    f = open(filename, "w")
    f.write("".join(newlines))
    f.close()



if __name__ == "__main__":

    if not os.path.exists("_tex"):
        os.makedirs("_tex")


    markdown_files = glob.glob("_posts/*.md")
    latex_files = []
    for markdown_file in markdown_files:
        print "<< ", markdown_file
        latex_file = os.path.join("_tex", os.path.basename(os.path.splitext(markdown_file)[0]) ) + ".tex"
        latex_files.append(latex_file)
        print ">> ", latex_file
        cmd = shlex.split("kramdown --input GFM %s --no-auto-ids --output latex" % markdown_file)
        # markdown to latex
        with open(latex_file, 'w') as fout:
            proc = subprocess.Popen(cmd, stdout=fout)

        proc.wait()
        # remove yaml-header from tex files and fix images
        clean_file(latex_file)
```

This creates a directory `_tex` and puts all the converted and cleaned tex files in it. The final step is to `\input`
them in a master latex file to produce the finale pdf documentation. 

## Tips

Things to keep in mind when writing the markdown files

- Always specify the language of code snippets. 
- use `$$`-syntax to write math-symbols.
- 
