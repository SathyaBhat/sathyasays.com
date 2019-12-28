---
title: Linux Switchover Guide
author: Bharath
type: post
date: 2008-12-20T05:39:04+00:00
draft: true
url: /?p=612
categories:
  - General
tags:
  - applications
  - Arch
  - boot
  - Brasero
  - cat
  - codecs
  - community
  - compiz
  - compiz fusion
  - CrossOver
  - DE
  - Desktop
  - desktop environment
  - desktop environments
  - distro
  - distros
  - dl
  - download
  - driver
  - drivers
  - dual
  - DVD
  - exe
  - ext2
  - ext3
  - FAT
  - FAT32
  - Fedora
  - file
  - filesystem
  - find
  - Firefox
  - forums
  - fun
  - fusion
  - GNOME
  - Google
  - grub
  - guide
  - guides
  - Home
  - icons
  - IM
  - install
  - intel
  - internet
  - KDE
  - Konqueror
  - linux
  - linux guide
  - LiveCD
  - LV
  - media
  - mount
  - move
  - moving
  - multimedia
  - net
  - New
  - newbie
  - NTFS
  - open source
  - opensolaris
  - openSuSE
  - Opera
  - Operating System
  - operating systems
  - os
  - package manager
  - partition
  - partitioning
  - Partitions
  - Pidgin
  - read
  - Resolution
  - rm
  - Screen
  - Screen Resolution
  - show
  - software
  - softwares
  - Solaris
  - SUSE
  - switch
  - switching
  - switchover
  - synaptic
  - tar
  - theme
  - themes
  - Ubuntu
  - Unity
  - UNIX
  - update
  - upgrade
  - user
  - ux
  - VLC
  - wallpaper
  - web
  - windows
  - WINE
  - X
  - xp
  - YaST
  - yum

---
**This is basically a guide for all those pals who are  planning to or already have switched over to Linux newly. I have not used Operating Systems (OS) other than Linux and Windows so this guide would mostly be on a Windows perspective.**.

**NOTE: This guide assumes that the reader already knows about and has some experience, in installing in general, an OS. This guide also assumes that you know what hardware your computer is made up of.****
  
** 

<p style="text-align: left">
  <p style="text-align: left">
    <strong>BEFORE YOU SWITCHOVER</strong>
  </p>
  
  <p>
    Linux environment may not be very comfortable to you as you are used to windows. Linux uses different  set of software, different GUI and different methods to perform a task. So, if you also want to get the services offered by Windows, it would be wise to do a dual-boot rather than removing Windows. And many Linux distributions come as a <a href="https://en.wikipedia.org/wiki/Live_CD">LiveCD</a> so it is better to try it before installing it. This way,  one may avoid installing what they do not actually want to install.
  </p>
  
  <p>
    <!--more-->
  </p>
  
  <p>
    Next, be careful while partitioning before or during the install. Linux will be needing a separate partition and a different <a href="https://en.wikipedia.org/wiki/File_system">filesystem</a> like ext3, ext2 etc. and CANNOT be installed in FAT32 or NTFS partitions used for windows (unless you&#8217;re up to some tricks). Though, <a href="https://en.wikipedia.org/wiki/Ubuntu">Ubuntu</a> has now brought a cool feature that lets you install it inside Windows while being in windows.
  </p>
  
  <p>
    One of the most disappointing thing in most <a href="https://en.wikipedia.org/wiki/Linux_Distro">linux distros</a> is that Windows users CANNOT USE EXE FILES. This is because the structures of how Windows and Linux are made different. But with the help of some software, you can run EXE files. Open Source <span style="text-decoration: line-through">emulator</span> <em>[Ed&#8217;s note: WINE is not an emulator.WINE is recursive acronym for WINE Is Not an Emulator]</em> WINE is the most famous. There are also ones like Cedega and Crossover<em>[Ed&#8217;s note: Again, these are based on WINE code and aren&#8217;t emulators] </em>which are commercial ones.
  </p>
  
  <p>
    There are three famous desktop environments in Linux that one can choose from &#8212; GNOME, KDE. and XFCE. They are both unique and different that a user may choose. If you have a  confusion on choosing, choose any one and install and try them. Whichever it is, you got to get use to them before using them full fledged.
  </p>
  
  <p>
    Linux distros may have little to lots of bugs in them. You will have to resist them if you definitely want to switchover. I am not in anyway discouraging, but I would like to disclose facts.
  </p>
  
  <p>
    <strong>INSTALLING LINUX</strong>
  </p>
  
  <p>
    This is the most important part. A more comprehensive guide on Installing Linux could be found <a href="https://sathyasays.com/linux-install-guide/">here</a> and its link on the home page of this site. Do not do it in any kind of hurry or recklessness. Do all of it with complete concentration. Be extremely careful when selecting partitions and configuring the key options.
  </p>
  
  <p>
    YOU NEED TO HAVE:
  </p>
  
  <p>
    *An installable Linux CD/DVD of any distro of your choice
  </p>
  
  <p>
    *A partition fully empty and important data backed up
  </p>
  
  <p>
    *Enough knowledge of what you have to do and what you are doing
  </p>
  
  <p>
    And, as the basic step insert and boot from your CD/DVD like how you will do for any other OS install. If It is a Live CD/DVD (try to get one if you don&#8217;t have) you actually work on a desktop and use the OS before even installing it! If you are dissatisfied or uncomfortable with it you can leave the Live CD desktop and reboot into your Hard Drive. No changes would have happened to whatever OS is already installed.
  </p>
  
  <p>
    If you want to install just open the text or graphical installer and follow the on-screen installation of the OS. During the install process you don&#8217;t have to keep taping your legs on the floor in a Live CD. You can play a game, browse the internet or anything you will be doing on a desktop after you install.
  </p>
  
  <p>
    <strong>AFTER THE INSTALL</strong>
  </p>
  
  <p>
    There could be problems during your install. Most of them are easily solvable with a search on the Internet. Or you post them in respective forums and ask any knowledgeable person you know. After a successful installation and reboot you will see a new <a href="https://en.wikipedia.org/wiki/Booting#Boot_loader">bootloader</a> mostly will be GRUB or LILO. They are bootloaders for Linux and they are used to boot into Linux or Windows
  </p>
  
  <p>
    First things first. Most of your drivers like sound driver, input device drivers etc. should be there automatically. Some of the drivers for certain devices like graphics cards for example, need  closed source drivers (also called restricted drivers, are provided by the manufacturers themselves) for full functionality of the device. Find out how to install and what devices to install those drivers for, through an internet search or asking a knowledgeable person. Restart, if necessary.
  </p>
  
  <p>
    In certain distros like Ubuntu programs like Jockey (Hardware Drivers) provide restricted drivers for Video Cards. They find and install the right driver for the right card, that is already tweaked by the community so that it is readily usable. In some unix-based OS like OpenSolaris (I don&#8217;t know about the close source one) bundle the driver along with the OS, so that it even works in the live CD!!!!! For some cards like Intel, drivers need not be installed explicitly in certain distros. They may be installed during the OS install. For certain other distros and cards you may need to download them from the website of manufacturers or the distro&#8217;s website. Some websites also make a list of card models and corresponding drivers to be used. So, I say you find out what hardware you have, what model, whether your distro provides tweaked drivers and if so how, where to download, which driver to download and how to get them working.
  </p>
  
  <p>
    Following the install of Graphics Card drivers it would be worthy to mention about <a href="https://en.wikipedia.org/wiki/Compiz_fusion">Compiz Fusion</a>. So if your graphics card drivers are installed successful, just do a google search on how to install and activate compiz fusion on your distro. There are umpteen guides over the internet for this.
  </p>
  
  <p>
    Next, you&#8217;ll have to install codecs for the more popular video and audio formats in case they are not provided with the installation medium due to legal restrictions.You can follow the guide <a href="https://sathyasays.com/multimedia-support-in-linux/">here</a>, to install them.
  </p>
  
  <p>
    Install/Upgrade all necessary software for your specific purposes. They can be installed and/or upgraded through a <a href="https://en.wikipedia.org/wiki/Package_manager">package manager</a> that comes with most distros. Most famous ones include YaST in OpenSUSE, Synaptic in Ubuntu, yum in fedora etc. Find out what software you need for what specific purpose. Most famous purposes and respective softwares include Firefox/Konqueror for web browsing, Pidgin/Kopete for Chatting, Open Office for office purposes, Brasero/K3b for cd burning, VLC/Totem/Kaffenine/Rhythmbox/banshee for multimedia and so on. Do not worry about any anti-virus stuff, Your Linux is already secure. Forget viruses spyware etc.
  </p>
  
  <p>
    WINE, used to run Windows applications, can be installed for the same purpose. It works well with a few application and available for most distros. The WINE website is <a href="https://winehq.org">https://winehq.org/</a> and a list of working and non-working software can be found in the WineAppDB in the site. Other commercial software like Cedega or Crossover can also be used at will.
  </p>
  
  <p>
    Its worth mentioning that your Linux partition will not be visible  under Windows.  Do not panic. This is happening because Windows doesn&#8217;t understand the file system, and so it did not mount (i.e. showing the contents of something inside a folder) it. You can check out Sathya&#8217;s post on <a href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/" target="_blank">how you can access your Linux partitions under Windows</a>.
  </p>
  
  <p>
    Start customising and using your Linux. Change the wallpaper. Set your screen resolution. Try new GUI themes from <a title="Gnome Look" href="https://gnome-look.org" target="_blank">Gnome Look</a>, <a title="KDE Look" href="https://kde-look.org/">KDE Look</a> and <a title="Xfce Look" href="https://xfce-look.org/">Xfce Look</a> for the respective desktops. Start placing desktop icons and other shortcuts. The more you explore, you will find out that Linux not something very alien but is just another OS serving the same purpose in a different way
  </p>
  
  <p>
    <strong>UNINSTALLING LINUX</strong>
  </p>
  
  <p>
    If you want to uninstall Linux just format your Linux partition an you are done. But in case you are getting a GRUB error screen or something, just follow my guide <a href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/">here</a>.
  </p>
  
  <hr />
  I have tried to make a guide that just orients a new user to Linux and provides the instructions to start using Linux. If you think I need to add something or for a doubt do drop a comment or e-mail me. This guide will constantly be updated as soon as I receive anything to add.  Thank you for reading my guide.
</p>
