---
layout: post
title:  "Merge Two PDFs"
date:   2020-01-04 10:36:44 -0300
categories: PDF Linux command-line
---
# Merge Two PDFs

Short post here. To merge two PDFs files into a single one, use ghostscript. You can do this
from a terminal with 

`gs -dBATCH -dNOPAUSE -q -sDEVICE=pdfwrite -sOutputFile=finished.pdf file1.pdf file2.pdf`