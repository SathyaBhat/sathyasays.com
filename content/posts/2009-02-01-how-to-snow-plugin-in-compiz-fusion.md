---
title: '[How-to] Snow Plugin in Compiz-Fusion'
author: Bharath
type: post
date: 2009-01-31T19:37:59+00:00
url: /2009/02/01/how-to-snow-plugin-in-compiz-fusion/
categories:
  - "Tips &amp; How-To's"
tags:
  - AIR
  - Arch
  - autumn
  - cairo
  - commands
  - compiling
  - compiz
  - distro
  - Dreamscene
  - exe
  - eye-candy
  - Fedora
  - file
  - find
  - forums
  - fusion
  - git
  - internet
  - linux
  - LV
  - open source
  - openSuSE
  - plugin
  - RIA
  - Sabayon
  - snow
  - SUSE
  - terminal
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - wallpaper

---
After a long time&#8217;s search over the internet for many days I finally figured out how to do this. Many may know this already but many may not too. And since I hate to compile programs from sourceI have found here a method that involves less of actual compiling. Since am a ubuntu user I only have tried this in ubuntu and not other distros.

**STEPS**

1. Install these packages:

compiz-bcop

compiz-dev

compizconfig-settings-manager

build-essential

libtool

libglu1-mesa-dev

libxss-dev

libcairo2-dev

git-core

2. You need a working directory say ~/compiz

3. When in your working directory, in terminal, execute this command:

> git clone git://anongit.compiz-fusion.org/fusion/plugins/snow

4. Download [this][1] file and extract its contents to your working directory

5. In your working directory now there will be a folder called snow. Change to that folder (~/compiz/snow in my case)

6. Execute these three commands one after the other:

> make
> 
> make clean
> 
> make install

7. Now in your CompizConfig Settings Manager you can find the snow plugin and activate it.

This may sort of resemble a dreamscene on your desktop and i really like it a lot. A snowy wallpaper could be suitable.

A small variant of this plugin called Autumn Plugin is [here][2] (Thanks to Patrick Fisher and ubuntu forums)

Thanks to elgilicious and ubuntu forums for [this][3]

_Ed&#8217;s note: Do we really need all of this ?  openSUSE, Fedora, Sabayon &#8211; all had Snow plugin without having to do any of this_

 [1]: http://oreaus.googlepages.com/snow.tar
 [2]: http://ubuntuforums.org/showthread.php?p=3792520
 [3]: http://ubuntuforums.org/showthread.php?t=768804