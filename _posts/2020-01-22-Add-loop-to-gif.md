---
layout: post
title:  "How to make gif animation to loop"
date:   2020-01-22 21:43:06 -0300
categories: image gif how-to
---

# How to make a gif animation to loop

Suppose you created a gif file, but unfortunately the tool you used to create
it does not allow (or maybe it would give too much work) to make it loop. The 
solution is then obviously edit it with a external tool designed to edit gif 
files.

If one look, for sure will find some GUI tools to do the job. But for my case,
I was looking for something simpler, that could be used from the command line.
The tool of choice is called `imagemagick`. My steps where the following

1. Usual install drill: `sudo pacman -Syu imagemagick`
2. To add the loop flag into the gif `magick -delay 100 -loop 0 input_file.gif output_file.gif`

The delay flag allow you to set the time between the frames (in the above 
example, a delay of 1 second) and the loop flag tells how many times the gif
will loop (the value zero means an endless loop).