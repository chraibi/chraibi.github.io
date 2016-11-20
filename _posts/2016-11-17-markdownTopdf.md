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
  ```python 
  for line in lines:
  # look for first appearance of "---"
      if not add_line and line.startswith("---"):
          add_line = 1
          continue # ignore this line
      if add_line:
            newlines.append(line)
  ```
  
- Fix the image paths:  replace liquid tags like `site.baseurl` by the an absolute path.

  ```python
  line = re.sub(r"\{\{\s* site.baseurl \s*\}\}", os.getcwd(), line)
  ```

Download the script that automates the above mentioned steps from [here](https://cst.version.fz-juelich.de/snippets/6)

The script creates a directory `_tex` and puts all the converted and cleaned tex files in it. 
The final step is to `\input{}` them in a master latex file to produce the finale pdf documentation. 

## Tips

Things to keep in mind when writing the markdown files

- Always specify the language of code snippets. 
- use `$$`-syntax to write math-symbols.
