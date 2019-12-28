---
title: Virtualization Concepts And Basics For Dummies
author: Sathya
type: post
date: 2008-01-21T19:20:56+00:00
url: /2008/01/22/virtualization-concepts-and-basics-for-dummies/
categories:
  - General
tags:
  - 3D
  - Apple
  - applications
  - basics
  - boot
  - cat
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - distro
  - distros
  - free
  - fusion
  - games
  - hassles
  - IM
  - install
  - KDE
  - Leopard
  - linux
  - mount
  - music
  - open source
  - openSuSE
  - os
  - RIA
  - rm
  - Screen
  - security
  - show
  - software
  - Super
  - support
  - SUSE
  - usb
  - user
  - ux
  - VirtualBox
  - virtualization
  - virtualizer
  - vm
  - VMWare
  - web
  - windows
  - X
  - Xen
  - xp

---
Virtualization is a concept most likely you will be familiar of.
  
Take an example. Consider PSCX. It&#8217;s an emulator, which allows you you to play PS2 games on a PC right? That&#8217;s basically virtualization at work. Virtualization is a fancy name for emulation. Virtualization software allows you to virtualize a machine, create a &#8220;virtual&#8221; PC &#8211; you can do anything on the virtual pc as you can do on a normal PC &#8211; Install an OS, run applications, compile applications, surf the web, the applications are limit less. So why virtualize you may ask?
  
Well that depends on what you want to do. If you&#8217;re a developer, wanting to test cross-platform applications(ie, applications that will run across multiple OS) virtualization provides you to do so without the hassles of actually installing the required OS.
  
Some terminology:

<!--more-->


  
**Host machine** &#8211; The actual physical machine, ie, your computer
  
**Guest machine** &#8211; The virtual machine, ie, the machine you&#8217;re virtualizing or emulating.
  
Or if you&#8217;re like me. I try out various Linux distros under virtualization. I try out different things(like Kernel compilation, etc) on my virtual system, so that my actual system doesn&#8217;t get broken.

Virtualization is also a great security boon, you can surf the web safely on the guest machine, without the fear of viruses/Trojans/Spyware/malware infecting your host system. There are lot of virtualizers available, one of the best being VMWare Workstation. The other very good virtualizer is VirtualBox, Unlike VMWare Workstation, VirtualBox is free and open source, and isn&#8217;t as heavy on the system as VMWare is.
  
Virtualization requires a speedy processor, and lots of RAM, as when you allocate certain amount of RAM, the entire chunk is dedicated to the guest machine. Say I create a virtual machine, I want to load Windows XP on it, and I allocate 256 MB RAM to it, now the entire chunk of 256MB is dedicated to the guest machine. So in order to the 256MB needed for the guest machine, you&#8217;ll also need decent amount of memory free so that your host machine also runs smoothly.

As I mentioned earlier there are lots of software available for Virtualization, most of them free.
  
For Windows, you have
  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VMWare Workstation(commercial, with 30 day trial)


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VMWare Server(free, but no sound/USB support)


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VirtualBox (free, openSource, very light on system)


  
Linux comes inbuilt with a virtualizer, in form of Xen Virtualization, but is a bit complicated to use
  
Other Virtualization software include
  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VMWare Server & Workstation


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VirtualBox


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> KEMU


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> QEMU


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> Bochs

Mac users also have virtualization options, in form of

<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> Apple&#8217;s BootCamp(now built into Leopard)


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> Parallels Desktop


  
<!-- s:arrow: -->

<img title="Arrow" src="http://www.tech2.com/forums/images/smilies/icon_arrow.gif" border="0" alt="Arrow" /><!-- s:arrow: --> VMWare Fusion

Here are couple of screentshots showing what a good system is capable of. I prefer Linux for Virtualization, because of it&#8217;s superior memory management.
  
<a class="postlink" href="http://img221.imageshack.us/my.php?image=virtualization1ye2.jpg" target="_blank"><img src="http://img221.imageshack.us/img221/2751/virtualization1ye2.th.jpg" alt="Image" /></a>
  
The above picture shows my Linux desktop on a 3d Cube(Compiz Fusion ROCKS!! FTW!)
  
On the left side of the cube you can see openSUSE booting, while on the right side you can see Windows XP desktop.

The next screenshot will make it even clearer.
  
<a class="postlink" href="http://img218.imageshack.us/my.php?image=virtualization2bo3.jpg" target="_blank"><img src="http://img218.imageshack.us/img218/9574/virtualization2bo3.th.jpg" alt="Image" /></a>

As seen from the screen, my 3d Desktop is folded out and on my single system, I&#8217;m running total of 4 OS&#8217;s simultaneously &#8211; (from left to right), PC BSD, KDE Four Live(on openSUSE), Windows XP and of course, openSUSE my host system.
  
Linux&#8217;s memory management is pretty obvious from this example, despite all these OS&#8217;s running(512MB for PC BSD, 512MB for KDE Four, 512 MB for XP) and despite Compiz Fusion running, I have over 250 MB free for my host machine and I can do all things &#8211; surf, listen to music, play with the desktop effects et all.