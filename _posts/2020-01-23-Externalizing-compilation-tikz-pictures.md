---
layout: post
title:  "Externalizing the compilation of Tikz images"
date:   2020-01-23 18:36:50 -0300
categories: image latex tikz
---

# Externalizing the compilation of Tikz images

My tool of choice to make an illustration when I am writing something
using LaTeX is Tikz. However, compiling a document, specially a large
one, or one with many complex figures, can be quite slow. Thus, the
solution is to "externalize" its compilation, i.e. you tell to your 
latex compiler (usually pdflatex) to create a separate pdf of the 
figure and then include it. Of course, you could do this manually,
but there is an smarter way of implementing this.

Assuming that you saved your figure in a separate file 
`MyFigure.tex`, a possible structure for your main tex file could be
 the following

```latex
\documentclass{article}
\usepackage{tikz} 

% This will enable externalization
\usetikzlibrary{external}
\tikzexternalize[prefix=figures_tikz/] % PDFs of your figures will 
                                       % be saved in this path

% Use this command when inputting your files, as to avoid the 
% default numbering scheme of Tikz, which is known toi get lost
% when you reorder figures
\newcommand{\inputtikz}[1]{\tikzsetnextfilename{#1}\input{#1.tex}}

\begin{document}
\inputtikz{MyFigure}
\end{document}
```

The mandatory commands to enable externalization are
`\usetikzlibrary{external}` and the `\tikzexternalize[prefix=path]`.
Finally, when compiling, you need to pass one more option to 
pdflatex:

```bash
pdflatex -shell-escape MainFile.tex
```

There is other two commands that are useful to use when you are 
editing a particular image:

* `\tikzexternaldisable` : Disable externalization for all 
  figures after this command
* `\tikzexternalenable` : Enables externalization for all 
  figures after this command

Thus, if I am working in a particular figure, I enclose it with 
a pair of disable/enable and when I am done working on it, I 
comment out these. 