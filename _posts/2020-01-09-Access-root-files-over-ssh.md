---
layout: post
title:  "Accessing a `.root` file over ssh"
date:   2020-01-09 19:57:09 -0300
categories: ROOT network ssh
---
# Accessing a `.root` file over ssh

You may face a situation where you need to access a `.root` file located in machine A from machine B.
If the file is small, the easiest solution maybe to copy the file from A to B. However, if the file
is not small and you need only a small chunk of data from it, it may be desirable to access it
remotely. ROOT offers an easy way to do this and I will show one way of doing it, even if you
do not have admin powers in computers A and B.

This post is adapted from [this presentation](https://agenda.infn.it/event/4933/attachments/39935/47100/Tutorial-3-IO-net.pdf), which I recommend everyone to read for further information.

I will assume you have 
[installed ROOT as in my previous post]({{ site.baseurl }}{% link _posts/2020-01-06-Install-ROOT.md %}).
It is specially important that
you have configured the build with the flag `-Dbuiltin_xrootd=ON`, since this compiles 
`xrootd`, the tool we will rely to achieve our goal.

The first step is to create a config file in the computer A, the one holding the data.
The file may have any name or extension, but a good suggestion is to place it inside
your home folder and name it `xrd.cf`. Its content must be

```
# Otherwise we cannot create the admin files
all.adminpath /tmp/xrootd/
all.pidpath /tmp/xrootd/
# Allow access to the following directories in readonly mode
# (add as many as needed, one directive per directory)
all.export /full/path/to/folder/with/data1 r/o
all.export /full/path/to/folder/with/data2 r/o
# Better to use a dedicate port
xrd.port 51094
```

For some reason, when you do `cmake --build . --target install`, the binaries anb libraries
needed for `xrootd` are not copied to their right place. Thus, to run it, we must add the 
libraries to the `LD_LIBRARY_PATH` environment variables and call it using the full path 
of the binary. Assuming you build ROOT inside `$HOME/.local/src/root_build`, you do

```bash
export LD_LIBRARY_PATH=$HOME/.local/src/root_build/lib:$LD_LIBRARY_PATH`
$HOME/.local/src/root_build/bin/xrootd -c xrd.cf
```

Now it is listening in port 51094 for incoming connections. In the computer B, we create an
SSH tunnel to the computer A

```bash
ssh -L 51094:hostnameA:51094 user@hostnameA
```

This locks your terminal in a login shell inside computer A, making easy to terminate the tunnel
by simply closing the terminal. You may run this inside a `screen` session to not 
bother you. Or, you may just create the tunnel in the background (I do not like this 
alternative, since it is harder to terminate it later)

```bash
ssh -f4N -L 51094:hostnameA:51094 user@hostnameA
```

Finally, inside root, to open the file, instead of using
```c++
TFile* f = new TFile("/path/to/file","READ");
```
you do
```c++
TFile* f = TFile::Open("root://localhost:51094//full/path/to/folder/with/data1/file.root","READ");
```
and proceed with your analysis as usual.

A final word of advice: using this method, your network speed may become your main bottleneck. Thus,
I find okay using this to read a histogram and plotting it. And it should be okay if your analysis
retrieves a small chunk of data and perform a lengthy calculation. However, if your problem
requires you to access data very often, then I prefer to perform analysis locally if possible.