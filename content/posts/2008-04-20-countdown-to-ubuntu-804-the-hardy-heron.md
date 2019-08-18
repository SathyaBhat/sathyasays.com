---
title: 'Countdown to Ubuntu 8.04: The Hardy Heron'
author: Sathya
type: post
date: 2008-04-19T19:05:56+00:00
url: /2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/
categories:
  - News
tags:
  - 2.22
  - 8.04
  - AIR
  - blog
  - boot
  - Brasero
  - BulletProofX
  - cat
  - DE
  - download
  - dual
  - DVD
  - exe
  - file
  - find
  - FOSS
  - fun
  - GNOME
  - gvfs
  - hardy
  - Hardy Heron
  - Heron
  - IM
  - install
  - iso
  - linux
  - LTS
  - menu
  - Nautilus
  - net
  - New
  - open source
  - Opera
  - os
  - partition
  - performance
  - PolicyKit
  - repo
  - repos
  - repository
  - RIA
  - rm
  - root
  - software
  - support
  - transmission
  - Ubuntu
  - Ubuntu 8.04
  - umenu
  - upgrade
  - user
  - ux
  - virtualization
  - vm
  - windows
  - Wubi
  - X
  - xorg
  - xp
  - XRAndR

---
It&#8217;s that time of the year. Everyone&#8217;s excited and looking forward to it. Ofcourse it&#8217;s the release of the next LTS version of Ubuntu, Ubuntu 8.04, aka Hardy Heron. So what&#8217;re new features expected in Hardy Heron you ask? Well here are some of them
  
<!--more-->

### Easier installation using Wubi

Wubi allows users to install and uninstall Ubuntu like any other Windows application. It does not require a dedicated partition, nor does it affect the existing bootloader, yet users can experience a dual-boot setup almost identical to a full installation. Wubi works with a physical CD or in stand-alone mode, by downloading an appropriate ISO to install from. It can be found on the root of the CD as Wubi.exe. A full installation within a dedicated partition is still recommended, but Wubi is a great way to try Ubuntu for a few days and weeks before committing dedicated disk resources.

### umenu

WinFOSS and the Windows open source software have been replaced by umenu, a simple launcher that lets the user install Ubuntu from Windows using Wubi, install Ubuntu to a partition without having to make their CD-ROM the first boot device

### Policy Kit

Policy Kit gives you more detailed control with user access on specific administrative task. For example, you can assign privilege for one user to access network controls but not software installation.

### **Software Upgrades**

  * Linux kernel 2.6.24 which brings in fixes liks dyntick support for amd64 and CFS(Completely Fair Scheduler)
  * GNOME 2.22: GNOME features lots of new features and improvements, such as a new Nautilus that uses GVFS as its backend. GVFS makes it possible to fix shortcomings of Nautilus such as the inability to restore files from trash, pause and undo file operations, and will make it possible to escalate user privileges for certain operations using PolicyKit for authentication. It also brings a significant performance boost to many operations.
  * XOrg 7.3 which features BulletProofX for failsafe graphics mode and GUI for XRandR. I&#8217;ve blogged about BulletProofX [previously][1] and on XRandR [here][2]
  * [Transmission][3] replaces Gnome Bittorrrent as the default bittorrent downloader in Ubuntu Hardy Heron LTS. Transmission is a lightweight bittorrent client with automatic banning feature and protocol encryption.
  * The new [Vinagre][4] VNC client is installed by default, replacing xvnc4viewer.
  * The [Brasero][5] CD/DVD burning application, which will complement the CD/DVD burning functions of Nautilus and replace the Serpentine audio CD burning utility.
  * Something which all virtualization maniacs like me have been waiting for: KVM is now officially maintained within the Ubuntu kernel.
  * For corporates: Active Directory support via [Likewise Open][6], available from the universe repository, enables seamless integration of Ubuntu within an Active Directory network.
  * And of course, the most obvious feature is the LTS..

So how will Hardy Heron cope up with the hype it&#8217;s been building? Let&#8217;s find out in couple of days time.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-289" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-289" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-289" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/04/20/countdown-to-ubuntu-804-the-hardy-heron/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.com/2007/09/07/new-failsafe-graphics-mode-for-ubuntu/
 [2]: http://sathyasays.com/2008/03/10/ubuntu-804-lts-gets-an-xrandr-gui/
 [3]: http://www.transmissionbt.com/
 [4]: http://www.gnome.org/projects/vinagre/
 [5]: http://www.gnome.org/projects/brasero/
 [6]: http://likewisesoftware.com/products/likewise_open/