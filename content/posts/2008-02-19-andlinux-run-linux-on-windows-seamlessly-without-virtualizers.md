---
title: andLinux – Run Linux on Windows seamlessly without virtualizers!
author: Sathya
type: post
date: 2008-02-19T17:22:30+00:00
url: /2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/
categories:
  - General
tags:
  - andLinux
  - applications
  - associations
  - beta
  - cat
  - CoLinux
  - commands
  - DE
  - Desktop
  - dl
  - driver
  - drivers
  - exe
  - FAT
  - file
  - fun
  - hard disk
  - icons
  - IM
  - install
  - internet
  - KDE
  - Konqueror
  - linux
  - login
  - menu
  - net
  - NTFS
  - open source
  - os
  - read
  - repo
  - rm
  - Screen
  - script
  - scripts
  - security
  - shell
  - synaptic
  - tar
  - terminal
  - twitter
  - Ubuntu
  - user
  - ux
  - virtualizer
  - Vista
  - vm
  - VMWare
  - warning
  - windows
  - X
  - xp

---
<p align="center">
  <img src="http://www.andlinux.org/img/logo_header.png" />
</p>

andLinux is a complete <a href="http://www.ubuntu.com/" target="_blank">Ubuntu</a> Linux system running seamlessly in Windows 2000 based systems (2000, XP, 2003, Vista [32-bit only])

<p align="justify">
  &nbsp;
</p>

<p align="justify">
  andLinux uses <a href="http://www.colinux.org/" target="_blank">CoLinux</a> as its core which is confusing for many people. CoLinux is a port of the Linux kernel to Windows. Although this technology is like VMware or Virtual PC, CoLinux differs itself by being more of a merger of Windows and the Linux kernel and not an emulated PC, making it more efficient. <a href="http://www.straightrunning.com/XmingNotes/" target="_blank">Xming</a> is used as X server and <a href="http://www.pulseaudio.org/" target="_blank">PulseAudio</a> as sound server.
</p>

andLinux is not just for development and runs almost all Linux applications without modification.

<p class="label">
  <a href="http://www.andlinux.org/img/screenshot.png" title="click to get a full size version of the image"><img src="http://www.andlinux.org/img/screenshot_small.png" border="0" /></a><br /> Screenshot (click to enlarge)
</p>

To start Linux applications, you may either use the XFCE Panel:

<p class="label">
  <img src="http://www.andlinux.org/img/xfce_panel.png" border="0" /><br /> The XFCE Panel
</p>

<p class="noskip">
  Or, you may choose to use the andLinux Launcher, which ships with andLinux since Beta 1. It consists of:
</p>

<li class="noskip">
  quicklaunch icons (e.g. for the file manager or the terminal)
</li>
<li class="noskip">
  a start menu in the system tray (next to the clock) which can be adapted to your own needs
</li>
<li class="noskip">
  so-called Explorer shell extensions, i.e. context menu item, with which you can open a folder in the file manager / terminal or open a file with the text editor
</li>
<li class="noskip">
  file type associations at your choice (e.g. for KOffice files, .tex / .dvi / .ps / .pdf files)
</li>
<li class="noskip">
  <tt>andCmd.exe</tt> to run linux commands from Windows scripts
</li>

<table align="center" border="0" cellpadding="0" cellspacing="10">
  <tr>
    <td>
      <p class="label">
        <img src="http://www.andlinux.org/img/quicklaunch_xfce.png" align="middle" border="0" /><br /> Quicklaunch icons (XFCE version)
      </p>
      
      <p class="label">
        <img src="http://www.andlinux.org/img/quicklaunch_kde.png" align="middle" border="0" /><br /> Quicklaunch icons (KDE version)
      </p>
      
      <p class="label">
        <img src="http://www.andlinux.org/img/xfce_menu.png" align="middle" border="0" /><br /> Start menu (XFCE version)
      </p>
    </td>
    
    <td>
      <p class="label">
        <img src="http://www.andlinux.org/img/kmenu.png" align="middle" border="0" /><br /> Start menu (KDE version)
      </p>
    </td>
  </tr>
  
  <tr>
    <td colspan="2">
      <p class="label">
        <img src="http://www.andlinux.org/img/explorer1.png" border="0" /><br /> Open a folder with Konqueror or Konsole
      </p>
    </td>
  </tr>
</table>

### Requirements {.noskip}

<li class="noskip">
  OS: Windows 2000 / XP / 2003 / Vista [32-bit only]
</li>
<li class="noskip">
  Memory: at least 128 MB (192 MB or more is recommended)
</li>
<li class="noskip">
  Hard disk space: 2.5 GB (XFCE version) / 4.5 GB (KDE version)<br /> Note that you need an NTFS file system (which is default since Windows 2000) because you can&#8217;t create files larger than 2 GB on FAT(32) file systems!
</li>
<li class="noskip">
  A good internet connection (to be able to install further applications)
</li>
<li class="noskip">
  Some basic Linux skills to proceed once andLinux is installed
</li>

### What you will get

<p class="noskip">
  You will get:
</p>

<li class="noskip">
  a fully functional Linux system, however without the usual desktop (you&#8217;ve already got one from Windows)
</li>
<li class="noskip">
  a second panel (e.g. at the top of your Windows desktop) or a second start menu (in the system tray next to the clock), from which you can start Linux applications
</li>
<li class="noskip">
  Linux applications and Windows applications can be used simultaneously and you can cut and paste text between them
</li>
<li class="noskip">
  apt / synaptic to install further applications
</li>

<p class="noskip">
  You will NOT get:
</p>

<li class="noskip">
  another desktop
</li>
<li class="noskip">
  the bench of applications that usually ship with Linux distributions (you have to fetch whatever you want)
</li>
<li class="noskip">
  a printer driver
</li>
<li class="noskip">
  trouble with further drivers ;-)
</li>

**<font color="red">Security warning:</font>** It is recommended to use andLinux only on single-user-PCs or in a trustworthy environment because the communication with the X-Server and the launcher is not secured, i.e., every user who can login to Windows can access andLinux.

This looks really interesting and promising! Am definitely going to try this out and report how it turns out

Thanks to @[chetanthaker][1] who [twittered][2] about this

Technorati Tags: <a href="http://technorati.com/tag/linux" class="performancingtags" rel="tag">linux</a>, <a href="http://technorati.com/tag/andlinux" class="performancingtags" rel="tag">andlinux</a>, <a href="http://technorati.com/tag/sathyasays" class="performancingtags" rel="tag">sathyasays</a>

 [1]: http://twitter.com/chetanthaker
 [2]: http://twitter.com/chetanthaker/statuses/726461112