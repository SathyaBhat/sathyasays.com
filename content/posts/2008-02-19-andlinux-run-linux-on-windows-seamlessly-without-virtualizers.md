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
  <img src="https://i2.wp.com/www.andlinux.org/img/logo_header.png?w=740" data-recalc-dims="1" />
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
  <a href="https://i1.wp.com/www.andlinux.org/img/screenshot.png" title="click to get a full size version of the image"><img src="https://i1.wp.com/www.andlinux.org/img/screenshot_small.png?w=740" border="0" data-recalc-dims="1" /></a><br /> Screenshot (click to enlarge)
</p>

To start Linux applications, you may either use the XFCE Panel:

<p class="label">
  <img src="https://i1.wp.com/www.andlinux.org/img/xfce_panel.png?w=740" border="0" data-recalc-dims="1" /><br /> The XFCE Panel
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
        <img src="https://i0.wp.com/www.andlinux.org/img/quicklaunch_xfce.png?w=740" align="middle" border="0" data-recalc-dims="1" /><br /> Quicklaunch icons (XFCE version)
      </p>
      
      <p class="label">
        <img src="https://i2.wp.com/www.andlinux.org/img/quicklaunch_kde.png?w=740" align="middle" border="0" data-recalc-dims="1" /><br /> Quicklaunch icons (KDE version)
      </p>
      
      <p class="label">
        <img src="https://i1.wp.com/www.andlinux.org/img/xfce_menu.png?w=740" align="middle" border="0" data-recalc-dims="1" /><br /> Start menu (XFCE version)
      </p>
    </td>
    
    <td>
      <p class="label">
        <img src="https://i1.wp.com/www.andlinux.org/img/kmenu.png?w=740" align="middle" border="0" data-recalc-dims="1" /><br /> Start menu (KDE version)
      </p>
    </td>
  </tr>
  
  <tr>
    <td colspan="2">
      <p class="label">
        <img src="https://i1.wp.com/www.andlinux.org/img/explorer1.png?w=740" border="0" data-recalc-dims="1" /><br /> Open a folder with Konqueror or Konsole
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

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-266" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-266" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-266" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/02/19/andlinux-run-linux-on-windows-seamlessly-without-virtualizers/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://twitter.com/chetanthaker
 [2]: http://twitter.com/chetanthaker/statuses/726461112