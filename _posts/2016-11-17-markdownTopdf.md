---
layout: post
title:  "Writing documentation code from markdown files"
image: '/assets/img/totoro.png'
date:   2016-11-16 21:14:00
description: 'Making JuPedSim Guide'
categories:
- JuPedSim
twitter_text: "Writing documentation code from markdown files"
serie: learn
---

For the documentation of  [JuPedSim](http://jupedsim.org) we decided to go with a `markdown`-based approach, 
where every single article is written in markdown and published using Jekyll on GitHub-Pages. 
Very simple approach that allows focusing on writing the docs without any technical distraction. 

However, somehow surprisingly, using the same `markdown` files to  produce a printable pdf file for 
the documentation is not as straightforward as expected. 

## A typical  markdown file

A markdown file used to document JuPedSim has three objects that need to be rendered correctly in the pdf file. 

- Images with liquid syntax

```
![Simulation using `jpscore` ]( { { site.baseurl  } }/img/kobe.gif)
```

- Code snippets 

```xml
<crossing>
	<vertex px="10.0" py="6.0"/>
</crossing>
```

- In text embedded latex like \$\$\alpha$$ or equations like 

\$\$
\alpha = \frac{\beta}{\gamma},
$$

should be rendered correctly.

## Solution 
In this [article](http://peterlu.github.io/2014/08/03/markdown_latex_pdf.html)
Peter J. Lu gives a nice summary what possibilities there are to convert markdown to pdf file and why there are 
a bunch of problems that you face when you do so.

The solution that he uses delivers the "best" possible result, but still requires some **manual** cleanup of the files. 

Here are the steps: 

- With `Kramdown` convert the markdown file to latex.

  ```python
  kramdown _posts/file.md --no-auto-ids --output latex > file.tex
  ```

- Cleanup `file.tex` by removing  the YAML headers:

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

## Result

the above mentioned criteria are all given in  this  [sample article](/2016-11-20-test-md2pdf.html) 

And here is the resulting [pdf file](https://fz-juelich.sciebo.de/index.php/s/yIANyTztEprayuI).

## Tips

Things to keep in mind when writing the markdown files

- Always specify the language of code snippets. 
- use `$$`-syntax to write math-symbols.
