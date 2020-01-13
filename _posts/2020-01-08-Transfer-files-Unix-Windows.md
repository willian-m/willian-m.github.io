---
layout: post
title:  "Transferring large amount files from a unix server to local NTFS external hards drive"
date:   2020-01-08 21:45:53 -0300
categories: Linux Windows NTFS rsync
---
# Transferring large amount files from a unix server to local NTFS external hards drive

Imagine the following situation: You have a remote server with a large amount of data (> 500 GB)
and you need to transfer this data for a local hard-drive. More specifically, an external 
hard-drive (connected to an USB port). The server is running a unix system (in my case CentOS)
and the local computer is running Windows, but have WSL installed. Also, the external hard-drive is formatted with
NTFS. Here is a possible approach to perform the transfer

1. Mount the external hard-drive in WSL in an empty folder named `d` in your 
home folder (assuming D: was the letter assigned 
by Windows to it): `sudo mount -t drvfs D: $HOME/d`
1. Install rsync if not installed yet (e.g. for Arch Linux `sudo pacman -Syu rsync`)
2. Copy the files with 
`rsync --stats --progress -A -a -r -v --no-perms -e ssh remote_hostname:path/to/origin/folder d/path/to/destination`

The files inside `path/to/origin/folder` will be copied to `d/path/to/destination/folder`. 
If you do not whish the `folder` to be created, you may append a `/` to the origin path.