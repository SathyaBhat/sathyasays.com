---
title: The best Linux system repair distribution gets better
author: Sathya
type: post
date: 2007-10-07T16:23:08+00:00
url: /2007/10/07/the-best-linux-system-repair-distribution-gets-better/
categories:
  - News
tags:
  - AIR
  - BIOS
  - boot
  - cat
  - DE
  - Desktop
  - driver
  - drivers
  - file
  - Gentoo
  - gtk
  - IM
  - linux
  - net
  - New
  - NTFS
  - os
  - partition
  - partitioning
  - RIA
  - rm
  - root
  - support
  - tar
  - terminal
  - update
  - upgrade
  - upgrading
  - user
  - ux
  - Vista
  - windows
  - X

---
<font size="2">If there&#8217;s a better system repair kit than the Gentoo-based SystemRescueCD Linux distribution, we haven&#8217;t seen it yet.</font>

<font size="2">The new 0.4 version of <a href="http://www.sysresccd.org/"> SystemRescueCd</a> was released on Oct. 4. This new edition focuses on disk partitioning, Vista support, and data rescue tasks. In the past, we&#8217;ve found SystemRescueCD to be the <a href="http://www.linux-watch.com/news/NS9297647757.html"> best of the best when it comes to repairing troubled systems</a>. We see every reason to believe that this version will be even better.</font>

 <font size="2">This edition is built on top of a customized 32-bit <a href="http://www.linux-watch.com/news/NS8173766270.html">Linux 2.6.22.09 kernel</a>. This kernel is named rescuecd. It also includes built-in support for the Reiser4 file system.</font>

 <font size="2">There is also just enough of a 64-bit kernel, rescue64, to use chroot on a 64-bit Linux system. The <a href="http://www.unixwiz.net/techtips/chroot-practices.html">chroot system call <strong>ch</strong>anges the <strong>root</strong> directory</a> of the current process and all child processes to a given path. For repair purposes, it is used to boot into an unwise unbootable system.</font>

<font size="2">If you&#8217;re a Windows user, don&#8217;t let the fact that this is a Linux-based repair tool keep you away. SystemRescueCD has long excelled at <a href="http://www.linux-watch.com/news/NS6659533347.html">repairing Windows systems</a>. With new support for the Vista “Offline NT Password & Registry Editor” and improved support for NTFS drives, SystemRescueCD is better than ever for what ails your Windows PCs.</font>

<font size="2">Another major improvement is that you can now use <a href="http://www.kegel.com/linux/pxe.html">PXE network booting</a>. With PXE, you can boot a troubled PC remote over your LAN into SystemRescueCD. This is great, for example, for a help desk repairing systems scattered over an office or campus. To get this to work, the PCs will need to be set to use wake-on-LAN and network boot. That&#8217;s been a standard PC feature since 2001, but it usually must be made active in the BIOS before you can use it.</font>

<font size="2">The distribution is also just easier to boot up, period. In the past, you often needed to manually set boot parameters for a successful boot-up. It wasn&#8217;t difficult, but it could be time-consuming. Now SystemRescueCD is much better at analyzing its hardware environment and automatically booting with the appropriate configuration and drivers.</font>

<font size="2">Starting with the version before this one, 0.3.8, the distribution also added serial communication tools: <a href="ttp://alioth.debian.org/projects/minicom">minicom-2.2</a>, an ANSI terminal program with ZModem support; <a href="http://sourceforge.net/projects/gtkterm">gtkterm-0.99.5</a>, another popular terminal program; and <a href="http://www.columbia.edu/kermit/ck80.html">ckermit-8.0.211</a>, a set of communication programs usually used for file transfers. These are invaluable for those times when you have no other way to get into a broken computer except through a serial port connection.</font>

<font size="2">Sometimes there are upgrades that you can ignore. The improvements aren&#8217;t big enough or upgrading the program is too much trouble. But, then there are updates that are so important or add so much to a program, you must make the upgrade. SystemRescueCD is a must-upgrade for anyone who does computer repair work.</font>

<font size="2">Source & Author: Steven J. Vaughan Nichols, <a href="http://desktoplinux.com/news/NS4076782266.html">DesktopLinux</a></font>