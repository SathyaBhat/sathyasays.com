---
title: Linux Mint 4.0 Daryna BETA 021 released
author: Sathya
type: post
date: 2007-10-28T15:03:16+00:00
url: /2007/10/28/linux-mint-40-daryna-beta-021-released/
categories:
  - News
tags:
  - 3D
  - acpi
  - Amarok
  - applications
  - Arch
  - beta
  - boot
  - cat
  - community
  - compiz
  - compiz fusion
  - cover
  - DE
  - Debian
  - Dell
  - Desktop
  - dl
  - download
  - downloads
  - driver
  - drivers
  - dual
  - file
  - Firefox
  - frontend
  - fusion
  - GNOME
  - Google
  - IM
  - indic
  - install
  - linux
  - LiveCD
  - LV
  - media
  - menu
  - Microsoft
  - move
  - multimedia
  - New
  - newbie
  - notes
  - NTFS
  - NVIDIA
  - os
  - partition
  - Partitions
  - PHP
  - Pidgin
  - read
  - repo
  - repos
  - repositories
  - rm
  - RMS
  - Screen
  - security
  - show
  - software
  - support
  - SUSE
  - synaptic
  - tar
  - Thunderbird
  - Ubiquity
  - Ubuntu
  - Unity
  - update
  - user
  - ux
  - wallpaper
  - windows
  - write
  - X
  - xorg

---
This is the first BETA release of Linux Mint 4.0, codename Daryna, based on Celena and compatible with Ubuntu Gutsy and its repositories.

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/daryna.png" rel="lightbox"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/daryna.png" /></a>
</p>

Daryna is using Gutsy&#8217;s package base (kernel 2.6.22, Gnome 2.20, OpenOffice 2.3, Thunderbird 2.0&#8230;etc).

<big><!--more-->

<br /> <span style="font-weight: bold; text-decoration: underline"></span></big><span style="font-weight: bold"><big style="text-decoration: underline">What&#8217;s new in Daryna</big></span>

<span style="font-weight: bold"><big style="text-decoration: underline"></big></span><span style="font-weight: bold">1. mintUpdate</span><span style="font-weight: bold"></span><span style="font-weight: bold"></span>

<span style="font-weight: bold">With mintUpdate you can now get automatic updates without compromising the stability of your system. Updates are assigned a security level which indicates how safe they are for you to apply. MintUpdate also brings you more information about the updates and the risks involved in applying them.</span>

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/mintupdate.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/mintupdate.png" /></a>
</p>

MintUpdate is also highly configurable and you decide which levels you want to see and which you want selected by default.

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/mintupdate2.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/mintupdate2.png" /></a>
</p>

The implementation of mintUpdate in Daryna follows the decision to remove the Ubuntu Update Manager in Celena because it didn&#8217;t give enough information about updates and assumed all updates were without risk for the user&#8217;s system.

<span style="font-weight: bold">2. mintInstall & the Software Portal</span>

MintInstall and the Software Portal were already available in Cassandra and Celena. Even though they were better alternatives than Click&#8217;n&#8217;Run, APTURL, PBIDir or the new SUSE initiative they failed to be noticed both by the press and by our own community. We asked ourselves why and came to the conclusion that there presence had not been made obvious enough. In Daryna, you can now interact with mintInstall without starting from the Portal. A link was added directly in the menu:

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/portal.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/portal.png" /></a>
</p>

And a new frontend to mintInstall now allows you to search the portal directly from your desktop:

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/portal2.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/portal2.png" /></a>
</p>

mintInstall itself was also made more intuitive and improvements were made to its interface.

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/portal3.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/portal3.png" /></a>
</p>

In the backend, mintInstall now also relies on Synaptic and brings improvements on how it handles downloads/installations of packages and hotplugging of repositories.

<span style="font-weight: bold">3. mintDesktop improvements</span>

mintDesktop got major improvements in terms of usability and now has an extra-feature which lets you restore the default splash-screens coming with Linux Mint for OpenOffice, Gimp and Amarok:

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/mintdesktop.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/mintdesktop.png" /></a>
</p>

<span style="font-weight: bold">4. Compiz Fusion</span>

Credits go to Xorg, Compiz Fusion and Ubuntu here for bringing us the best 3D effects available and activated out of the box in Daryna. We know how much you like these technologies so we also included the Compiz Fusion Setting Manager:

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/compiz.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/compiz.png" /></a>
</p>

<p style="text-align: center">
  <a href="https://linuxmint.com/pictures/screenshots/daryna/compiz2.png"><img src="https://linuxmint.com/pictures/screenshots/daryna/thumbnails/compiz2.png" /></a>
</p>

**Note: The Restricted Manager was improved and should be able to bring 3D support to all nVidia cards. Envy is being developed at the moment to include the new ATI drivers released by AMD and will be included in the next BETA or in the stable release of Daryna.**

<span style="font-weight: bold">5. Upstream improvements</span>

&#8211; Improvements made in Linux Mint 3.1 Celena: [https://www.linuxmint.com/rel_celena.php][1]
  
&#8211; Upstream improvements in Gnome 2.20: <https://www.gnome.org/start/2.20/notes/en/>
  
&#8211; Upstream improvements in Ubuntu 7.10: <https://www.ubuntu.com/getubuntu/releasenotes/710tour>
  
&#8211; Upstream improvements in the Linux kernel 2.6.22: [https://kernelnewbies.org/Linux\_2\_6_22][2]

<big style="text-decoration: underline"><span style="font-weight: bold">What makes Daryna ideal for the desktop?</span></big>

  * Out of the box multimedia support
  * Microsoft Windows Integration (Dual-boot, NTFS read/write support, Migration Assistant)
  * One-Click install system (Linux Mint Software Portal, mintInstall)
  * Easy file-sharing (mintUpload)
  * Desktop features, Control Center, mintMenu
  * 3D Effects
  * Great configuration tools
  * Great selection of default applications (OpenOffice, Firefox, Thunderbird, Gimp, Pidgin, XChat, Amarok..etc)
  * Solid package base (Google Earth, Picasa, Skype.. a lot of important software present in the repositories or in the Linux Mint Software Portal, compatibility with all Ubuntu Gutsy repositories and most Debian packages)

<big style="text-decoration: underline"><span style="font-weight: bold">Known issues in Daryna</span></big>

&#8211; Envy is not up to date as Alberto Milone is currently developing a new version to support the new ATI drivers.

&#8211; On computers with Dell Recovery Partitions: Manual Install might not work in the liveCD installer. To fix this issue: &#8220;apt purge ubiquity; apt clean; apt install ubiquity&#8221; then perform the installation and restore the sources.list from the liveCD to the installed system.

&#8211; On some hardware with ATI/nVidia cards: If the liveCD boots all the way to Gnome but hangs and just shows the mouse pointer and eventually the wallpaper, restart the liveCD, press F6 and change the options &#8220;quiet splash &#8211;&#8221; with &#8220;nosplash noapic noacpi &#8211;&#8220;.

 [1]: https://linuxmint.com/rel_celena.php
 [2]: https://kernelnewbies.org/Linux_2_6_22
