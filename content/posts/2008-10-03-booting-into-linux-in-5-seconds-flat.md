---
title: Booting into Linux in 5 seconds Flat!
author: Sathya
type: post
date: 2008-10-03T09:20:53+00:00
url: /2008/10/03/booting-into-linux-in-5-seconds-flat/
categories:
  - News
tags:
  - ASUS
  - boot
  - bootup
  - cat
  - DE
  - dl
  - driver
  - drivers
  - Fedora
  - file
  - filesystem
  - find
  - HAL
  - IM
  - license
  - linux
  - Linux Plumbers Conference
  - LPC
  - LTS
  - Moblin
  - net
  - New
  - "O'Reilly"
  - open source
  - PowerTOP
  - read
  - rm
  - Screen
  - security
  - support
  - sync
  - tar
  - Ubuntu
  - ux
  - X

---
At the recently held Linux Plumbers&#8217; Conference, 2 Linux developers,  [Arjan van de Ven][1] and Auke Kok, demonstrated a Linux system booting in five seconds flat. To demonstrate this, they used an Asus EEE PC using a modified [Fedora][2] and modified [Moblin][3]. In-fact the bootup was so fast that the they actually had to hold the EEE PC, as the bootup was completed well before the projector could warm up and sync.

To achieve this, they had to look up and identify what was slowing down the system, for this they used a tool, [Bootchart][4], by Ziga Mahkovec, which displays the order of the booting sequence, which modules are taking how much time amongst other details. 

<!--more-->

### What&#8217;s taking so much time?

From the bootchart analysis, the following time-wasting components were identified:

  * 1 Full Second in starting the loopback device and checking if all network interfaces are loopback
  * 2 seconds to start sendmail
  * Specifically in Fedora, setroubleshootd, atool used to find problems with Security Enhanced Linux configuration &#8211; which took up 5 seconds
  * Splashscreens taking up some extra precious seconds
  * In Ubuntu, modprobe took another 12 seconds, adding of license restricted drivers another 2.5 seconds, and Ubuntu&#8217;s GDM taking 2.5 seconds to display the background image

### How did they do it ?

Ajan and Aike did some changes to the way modules are being loaded, mainly

 

  * All modules required for boot were built into kernel, so that the time is not wasted in modprobe-ing
  * Incorporating ACHI changes and starting ACHI and UHCI initialization at the some time
  * Inclusion of a patch to support readahead, so that kernel keeps track of which blocks to read at boot, and makes it available when booting
  * Changing the order of tasts that init handles , so that the following three things are done at the same time
>   * a readahead process to read blocks from disk so that they&#8217;re cached in memory
>   * the filesystem check
>   * starting of HAL and udev for hot-plugged devics
  * Making lot of changes to X, to cut startup time

<div>
  As a result of all of the above steps, the boot time is cutdown drastically.
</div>

<div>
  Note that the above results were obtained an EEE PC which has a SSD, but Arjan states that he&#8217;s obtained a 10-second bootup time on his Thinkpad using a traditional HDD
</div>

<div>
  For more detailed info regarding the same, do read up on LWN&#8217;s <a href="http://lwn.net/Articles/299483/" target="_blank">article on the same.</a>
</div>

<div>
  Also catchup on an interview Arjan gave to <a href="http://broadcast.oreilly.com/2008/09/how-powertop-latencytop-and-fi.html" target="_blank">O&#8217;Reilly News.</a>
</div>

 [1]: http://www.fenrus.org/
 [2]: http://fedoraproject.org/
 [3]: http://www.moblin.org/
 [4]: http://www.bootchart.org/