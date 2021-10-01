---
title: Mounting .iso and .mds/mdf Files in Linux
author: Sathya
type: post
date: 2007-12-15T05:20:50+00:00
url: /2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/
categories:
  - News
tags:
  - '*buntu'
  - commands
  - console
  - distro
  - DVD
  - file
  - images
  - indic
  - iso
  - linux
  - mdf
  - mds
  - mounting
  -   - open source
  - root
  - show
  - software
  - sudo
  - terminal
  - tutorials
  - Ubuntu
  - windows

---
There are lots of times where you'd want to mount a CD/DVD image. Say your friend who uses his Windows box has given you a .iso file or a .mds/mdf file, created using Alcohol 120%. How would you mount them in Linux? Using the Terminal and making use of the [loop device][1],there is no need for any external software tools and utlities.

Here's the steps:

  1. Open the Terminal/Console.
  2. Switch to root user(mounting more often than not requires root privileges, we'll have a look as to how make media user-mountable later) by typing **<font color="#008000">su root</font>** *buntu users and others distros in which the root account is disabled, can skip this step.
  3. Type <font color="#008000">mount -o loop -t iso9660 /windows/movies/movies.mdf /movies/ </font> For users of distros where root account is disabled(like Ubuntu) prefix sudo to the above. So the command is <font color="#008000">sudo mount -o loop -t iso9660 /windows/movies/movies.mdf /movies/</font>

If the above command looks confusing,it's pretty simple! Let's dissect it.

mount command is pretty obvious, it's the commnad used for mounting storage media and images of storage media.

-o loop(note that o is the letter o not the numeral zero, ie, 0) instructs the mount command to use the loopback device. -o stands for option, loop indicates loop back device. Intuitive, ain't it?

-t iso9660 instructs the mount command that the image is of iso9660 format.

The next argument is the path to where the .mdf file is located.

The last argument is the path to which directory the media must be mounted.

The image below shows an example.

<p align="center">
  <a href="https://i.sathyabh.at/ss/2007/12/mount.jpg" title="mount.jpg"><img src="https://i.sathyabh.at/ss/2007/12/mount.thumbnail.jpg" alt="mount.jpg" /></a>
</p>

<p align="left">
  If all goes well, you shouldn't be getting any messages, as in the image. For .iso files, the steps are the same, just replace the .mdf file by the .iso file. The above method should work for CloneCD's .ccd and Nero's .nrg files(I remember it worked long time ago, not so sure though, if anyone can confirm this it'd be great!)
</p>

 [1]: https://en.wikipedia.org/wiki/Loop_device
