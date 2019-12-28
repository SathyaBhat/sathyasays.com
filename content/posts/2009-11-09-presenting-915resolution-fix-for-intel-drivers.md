---
title: Presenting 915resolution — Fix for Intel Drivers
author: Bharath
type: post
date: 2009-11-09T11:24:49+00:00
url: /2009/11/09/presenting-915resolution-fix-for-intel-drivers/
categories:
  - "Tips &amp; How-To's"
tags:
  - 915resolution
  - chipset
  - commands
  - DE
  - Desktop
  - driver
  - drivers
  - install
  - intel
  - Karmic
  - linux
  - move
  - onboard
  - open source
  - os
  - package manager
  - read
  - repo
  - repos
  - Resolution
  - rm
  - Screen
  - Screen Resolution
  - tar
  - Ubuntu
  - VGA
  - X
  - xorg

---
This article appears too late i suppose in this site. Many know about it already. Just in case, i am posting it.

So if your xserser-xorg-video-intel is not that satisfactory to you, or if it doesn&#8217;t give the right screen resolution, just use this. If available in repos use it, if not use [this link][1]. You will have to remove xserver-xorg-video-intel either manually or through package manager. Then after installation restart Xserver (Ctrl+Alt+Backspace; [Enable it thus in Karmic][2])

That should bring the resolution right or at least make it better.

Thanks to these articles and in case of problems please follow the links:

[The PAINLESS way to set Screen Resolution for Intel Chipsets][3]

[Can&#8217;t change resolution with 915resolution][4]

[Finally got desktop effects working (915resolution + xorg.conf)][5]

 [1]: https://www.freshnet.org/debian/hoary/915resolution_0.5-2_i386.deb
 [2]: https://sathyasays.com/2009/11/08/enable-xserver-shortcut-ctrlaltbackspace-in-ubuntu-9-10-karmic-koala
 [3]: https://ubuntuforums.org/showthread.php?p=2113867
 [4]: https://ubuntuforums.org/showthread.php?t=450638
 [5]: https://makingtheswitch.wordpress.com/2007/05/13/finally-got-desktop-effects-working-915resolution-xorgconf/ "Permanent Link to Finally got desktop effects working (915resolution + xorg.conf)"
