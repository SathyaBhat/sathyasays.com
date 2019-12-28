---
title: 'Ubuntu 8.04 “Hardy Heron”  Alpha 2 Released'
author: Sathya
type: post
date: 2007-12-23T19:20:01+00:00
url: /2007/12/24/ubuntu-804-hardy-heron-alpha-2-released/
categories:
  - News
tags:
  - 8.04
  - applications
  - boot
  - cat
  - community
  - DE
  - Desktop
  - download
  - file
  - find
  - GNOME
  - hardy
  - Hardy Heron
  - Heron
  - IM
  - install
  - iso
  - keyboard
  - kubuntu
  - laptop
  - Launchpad
  - linux
  - menu
  - moving
  - net
  - New
  - open source
  - os
  - read
  - repo
  - Resolution
  - show
  - software
  - support
  - torrents
  - Ubuntu
  - Ubuntu 8.04
  - Unity
  - update
  - upgrade
  - upgrading
  - user
  - ux
  - X
  - xorg
  - xp
  - Xubuntu

---
The Ubuntu developers are moving very quickly to bring you the absolute latest and greatest software the Open Source Community has to offer. Hardy Heron Alpha 2 is the second alpha release of Ubuntu 8.04, and with this new alpha release comes a whole host of excellent new features.

**Note: This is still an alpha release. Do not install it on production machines. The final stable version will be released in April 2008.**

### <u>In General</u>

These features are showcased for your attention. Please test them and report any bugs you find. If you want to see what the developers have cooking for the next alpha release take a look through the hardy blueprint page  <https://blueprints.launchpad.net/ubuntu/hardy>

### Upgrading from Ubuntu 7.10

To upgrade from Ubuntu 7.10, run &#8220;update-manager -d&#8221; using the update-manager package from gutsy.

### Xorg 7.3

The latest Xorg is available in Hardy, Xorg 7.3, with an emphasis on better autoconfiguration without config files.

### Linux kernel 2.6.24

Alpha 2 includes the 2.6.24-2.4 (2.6.24-rc5-based) kernel. This brings in significant enhancements and fixes that have been merged in the last few months into the mainline kernel. Among these is the introduction of dynticks support for amd64, bringing the same power savings already available on 32-bit systems to 64-bit laptops and desktops.

### PulseAudio

Alpha 2 includes [PulseAudio][1]{.external} enabled by default. Some non-GNOME applications still need to be changed to output to pulse/esd by default and the volume control tools are still not integrated.  <https://blueprints.launchpad.net/ubuntu/+spec/cleanup-audio-jumble>{.external}

### Download Alpha 2

Get it while it&#8217;s hot. ISOs and torrents are available at:

<li style="list-style-type: none">
  <a href="https://cdimage.ubuntu.com/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/releases/hardy/alpha-2/</a> (Ubuntu)<br /> <a href="https://cdimage.ubuntu.com/kubuntu/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/kubuntu/releases/hardy/alpha-2/</a> (Kubuntu)<br /> <a href="https://cdimage.ubuntu.com/edubuntu/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/edubuntu/releases/hardy/alpha-2/</a> (Edubuntu)<br /> <a href="https://cdimage.ubuntu.com/jeos/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/jeos/releases/hardy/alpha-2/</a> (Ubuntu JeOS)<br /> <a href="https://cdimage.ubuntu.com/xubuntu/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/xubuntu/releases/hardy/alpha-2/</a> (Xubuntu)<br /> <a href="https://cdimage.ubuntu.com/gobuntu/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/gobuntu/releases/hardy/alpha-2/</a> (Gobuntu)<br /> <a href="https://cdimage.ubuntu.com/ubuntustudio/releases/hardy/alpha-2/">https://cdimage.ubuntu.com/ubuntustudio/releases/hardy/alpha-2/</a> (UbuntuStudio)
</li>

### Caveats

As expected during early development snapshots, there are several known bugs that users are likely to run into with Hardy Alpha 2. We have documented them here for your convenience along with any known workarounds, so that you don&#8217;t need to spend time reporting these bugs again:

  * Due to the X server failing to provide a configuration file, the keyboard selection made during install will not be carried over to the installed system. <https://launchpad.net/bugs/173008>{.external}
  * Video problems have been reported with the 64-bit (amd64) version of Edubuntu desktop. As a workaround, users can manually specify a video resolution at the boot menu. <https://launchpad.net/bugs/173130>{.external}

Technorati Tags: <a href="https://technorati.com/tag/linux" class="performancingtags" rel="tag">linux</a>, <a href="https://technorati.com/tag/opensource" class="performancingtags" rel="tag">opensource</a>, <a href="https://technorati.com/tag/Ubuntu" class="performancingtags" rel="tag">Ubuntu</a>, <a href="https://technorati.com/tag/Hardy%20Heron" class="performancingtags" rel="tag">Hardy Heron</a>

 [1]: https://pulseaudio.org/
