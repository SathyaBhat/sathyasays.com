---
title: A Look At Ubuntu Gutsy Gibbon
author: Sathya
type: post
date: 2007-12-09T19:50:54+00:00
url: /2007/12/10/a-look-at-ubuntu-gutsy-gibbon/
categories:
  - Reviews
tags:
  - AIR
  - ALSA
  - Arch
  - blog
  - boot
  - compiz
  - compiz fusion
  - DE
  - Dell
  - dl
  - download
  - driver
  - drivers
  - DVD
  - file
  - find
  - Firefox
  - fusion
  - Google
  - Gutsy Gibbon
  - IM
  - Inspiron
  - install
  - intel
  - internet
  - linux
  - login
  - magazine
  - media
  - menu
  - mount
  - moving
  - Mozilla
  - Mozilla Firefox
  - net
  - New
  - newbie
  - Novell
  - NVIDIA
  - open source
  - openSuSE
  - os
  - package manager
  - Pidgin
  - plugin
  - rm
  - RMS
  - Screen
  - software
  - SUSE
  - tar
  - Ubuntu
  - upgrade
  - user
  - ux
  - views
  - X
  - xp

---
Ubuntu Gutsy has been receiving a huge amount of hype and fan fare recently, and I&#8217;ve been following Gutsy closely, from Ubuntu Fridge&#8217;s 10 Rocking Features in 10 Days to fellow bloggers and Linux users posts on Gutsy. Naturally after their Feisty launch, expectations were high(from my side). Now I&#8217;m not Ubuntu&#8217;s biggest fan(I&#8217;m a SuSE fellow, Novell haters, meh!), but I appreciate what Ubuntu has been doing for newbie Linux users in general.
  
I was patiently waiting for the December issue of [CHIP][1] magazine and picked it up immediately when it hit the stands, ripped apart the packaging and took out the DVD(yup, that&#8217;s right CHIP this month had a bootable DVD of Ubuntu Gutsy :D ) and started about installing it. Launching into the live environment took a good 2 minutes, uncharacteristic of Ubuntu.
  
<!--more-->


  
Also missing was the familiar Ubuntu login sound. Upon having a look at dmesg contents I realized that my sound card was.. for lack of better word, semi-detected. So ineffect, although it was detected, I wasn&#8217;t able to use it. I dismissed this as a one off incident and started installing it. The installer was the familiar 7-step installer. Something which is desperately missing is an install-time package manager which allows you to select which allows you to select the packages \*you\* want to install. Moving on,the installation was completed in about 30 minutes. After the install was done, I booted out from the live environment to the installed environment. Booting into the install environment again, the sound was disabled. Apparently the version of [ALSA][2] bundled with Ubuntu has problems with Intel&#8217;s HDA codec. Turning to my Google I was able to find [a solution to the problem][3]. Never expected Ubuntu to have a problem with a common hardware(though in all fairness, it&#8217;s ALSA with the bug, not Ubuntu).

A nice feature is that the moment you boot into the installed environment, and if there are some hardware which would require proprietory drivers, such as NVIDIA graphics card in my case, the Restricted Drivers Manager immediately informs you that such a driver is available and prompts you to download/install them from Internet/DVD. The Deskbar has the Nice Trakker feature, which are Nifty additions, but still they are nowhere close to as useful as openSUSE&#8217;s SLAB menu. Compiz Fusion is enabled by default, but only a limited set of plugins where active, few notably absent being the Cube and Scale plugin. I can understand why Cube was skipped, but why the Scale plugin? That&#8217;s one of the most useful and productive plugins!

Hardware detection wise, Gutsy was able to detect all of the hardware of my Dell Inspiron 1520, expect for the sound card. Another weird and irritating thing with Gutsy was that it would randomly increase the brightness of LCD screen, for no apparent reason, without me hitting any button. I noticed that this would happen whenever CPU frequency scaling would take place. Very irritating indeed!

Software wise, there&#8217;s no difference between the DVD and CD edition, atleast in terms of installed footprint. The usuals-Mozilla FireFox, Pidgin, OpenOffice.org, The GIMP, RhythmBox, Totem, are all present. In addition the DVD also had version 100.14 of NVIDIA&#8217;s drivers, sparing me the ordeal of a download.

Overall Gusty is a nice release. The new features(Deskbar, Trakker, BulletProof X for failsafe X onfiguration, AppArmour profiles) are worth the upgrade from Feisty to Gutsy. Me however will be sticking to the green Lizard, openSUSE 10.3, as Gusty offers nothing much to me compared to what openSUSE is offering, and working in any OS other than openSUSE 10.3 makes me realize how vital and useful the SLAB menu and integrated search feature is!

 [1]: https://www.chip-india.com
 [2]: https://en.wikipedia.org/wiki/Advanced_Linux_Sound_Architecture
 [3]: https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/
