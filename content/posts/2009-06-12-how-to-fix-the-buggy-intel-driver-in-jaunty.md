---
title: '[How-to] Fix the Buggy Intel Driver in Jaunty'
author: Bharath
type: post
date: 2009-06-12T15:49:40+00:00
url: /2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/
categories:
  - "Tips &amp; How-To's"
tags:
  - codecs
  - commands
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - driver
  - drivers
  - eye-candy
  - find
  - how-tos
  - install
  - intel
  - intrepid
  - Jaunty
  - linux
  - music
  - open source
  - os
  - tar
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - videos
  - VLC
  - X
  - xorg

---
So this is a short post on one pestering problem. If youre using Jaunty and find this problem then use the link that follows.

When i installed Jaunty i had problems (as usual). One of them was this. First off, videos wont play in any video player. Codecs are in place, no doubt. But the player would go crashing down. Even vlc, which uses a seperate set of codecs fails :(

Then, desktop effects wont enable. No matter what. An irritating piece of  thing.

But it was so queer that when rhythmbox (may be others too; i dont know) starts playing (not just open but playing) videos work! But i dont think video players should be dependent on music players.

So what worked for me was I rolledback to intrepid&#8217;s version (2.4) version of xserver-xorg-video-intel. Now no problems videos play and compiz is enabled.

[Click here][1] to find out how to revert to the 2.4 version.

Hope this helps.

 [1]: https://wiki.ubuntu.com/ReinhardTartler/X/RevertingIntelDriverTo2.4