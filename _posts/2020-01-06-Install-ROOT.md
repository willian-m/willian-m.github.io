---
layout: post
title:  "Guide: Compiling and installing CERN's ROOT from source"
date:   2020-01-06 20:30:07 -0300
categories: ROOT Guide 
---
# Guide: Compiling and installing CERN's ROOT from source

Each time I get into a new system, I face myself wanting to compile CERN's ROOT
from source. There are some reasons I do so instead of using pre-compiled binaries

1. Binaries distributed with your distribution may not be up to date
2. I may not have super user access to the computer
3. If needed, I can control what to install

For this guide, I will assume all dependencies needed for installation are met.

# 1. Getting source files

For the sake of keeping things organized, I usually create a `.local/src` folder inside my 
home folder. Then, you may clone ROOT's git repository inside it

```bash
git clone http://github.com/root-project/root.git
```

If you had already cloned, you may just pull the last changes (`git pull origin master`).

You may check the versions available by listing the tags (`git tag`). I recommend checking the 
github page and [ROOT's download page](https://root.cern.ch/downloading-root) for you to decide
which version you will use. I recommend using only Pro (from Production) releases. Once you 
decided which version to use, you must checkout to the release tag, e.g. `git checkout v6-18-04`.

Now, outside of the repository folder, create a `build_root`. Here is where you will compile ROOT.
Go to this folder and configure the build

```bash
cmake -Dbuiltin_xrootd=ON -DCMAKE_INSTALL_PREFIX=$HOME/.local path/to/source
```

The `-Dbuiltin_xrootd=ON` flag configures the build of the `xrootd` along root and
`-DCMAKE_INSTALL_PREFIX=$HOME/.local` tells where root will be installed. `xrootd` is a service
you may run in a computer to allows you logged in a remote client to access your `.root` files
and performs your analysis plots without copying the entire file content. I talk more about 
`xrootd` usage in [this post]({{ site.baseurl }}{% link _posts/2020-01-09-Access-root-files-over-ssh.md %}).

Now 
we build it with

```bash
cmake --build . -- -jN
```

where N is the number of available cores. Be patient, this may take a while.

Once it is finished, you may test if the build is working by executing `./bin/root`. If
everything is in working order, you may install it with

`cmake --build . --target install`

Last step, place at your `$HOME/.bashrc` the line `source $HOME/.local/bin/thisroot.sh` (assuming you use bash, else you must put this on the appropriate start session script of your shell).

Bonus: Every time you start ROOT, it will display a splash screen. This slows down its load time. Thus,
I advise placing the following alias in your `.bashrc` to speed up things: `alias root="root-l"` 


