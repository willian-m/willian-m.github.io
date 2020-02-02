---
layout: post
title:  "CPU cost by operation type"
date:   2020-01-16 20:14:36 -0300
categories: c++ performance external-reference infographic
---
# CPU cost by operation type

I found 
[this nice infographic](http://ithare.com/infographics-operation-costs-in-cpu-clock-cycles/) 
of operation costs of a given operation inside a program. Useful for
deciding: should I do `a/2.0` or `a*0.5`?

The bottom line I learned from the post

- Addition/subtraction is almost free.
- Writing to memory is almost free as well.
- Multiplication is way cheaper than division
- The compilers try to guess what is the "right" branch of an if.
  Thus, if you have condition A executed 90 % of the time, it is 
  best for it to top evaluate condition A to true.
- Performing a function call does cost CPU (~ the same amount as 
  a division).
- Local variables are preferable to global ones.
- Allocating memory to an object is *very* expensive.
- Reading things from main RAM is *very* expensive as well. That is 
  why local variables are preferable. They are more likely to be in a 
  cache than in RAM.

