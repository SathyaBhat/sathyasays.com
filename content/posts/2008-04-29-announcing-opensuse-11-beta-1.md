---
title: Announcing OpenSUSE 11 Beta 1
author: Sathya
type: post
date: 2008-04-29T04:33:58+00:00
url: /2008/04/29/announcing-opensuse-11-beta-1/
categories:
  - News
tags:
  - /dev
  - 2.22
  - 9.10
  - AA
  - apps
  - beta
  - boot
  - DE
  - download
  - driver
  - DVD
  - find
  - GNOME
  - HAL
  - IM
  - images
  - install
  - KDE
  - KDE4
  - license
  - linux
  - LiveCD
  - LTS
  - media
  - menu
  - move
  - net
  - NetworkManager
  - New
  - NVIDIA
  - open source
  - openSuSE
  - openSUSE 11
  - openSUSE 11.0
  - os
  - PackageKit
  - PolicyKit
  - Qt
  - rm
  - root
  - rpm
  - Samba
  - Screen
  - show
  - software
  - SUSE
  - switch
  - tar
  - testing
  - update
  - user
  - ux
  - VirtualBox
  - X
  - Xen
  - YaST
  - zypper

---
Last week,  the openSUSE team announced the first Beta release of openSUSE 11.0! Some of the many  enhancements and features in the new release include  the incredibly fast package management (libzypp), KDE 3.5.9 and 4.0.3, GNOME 2.22.1, a beautiful new installer, live CDs and much more.

## What’s New

<!--more-->

The openSUSE 11.0 beta 1 includes quite a few changes and new features that users will find interesting, including:

**KDE 4 and KDE 3.5:** The openSUSE 11.0 beta 1 includes KDE 4.0.3, which includes a number of [new features, fixes, and optimizations][1]. In case you are still hesitant to move to KDE4, the beta includes an installation option for KDE 3.5 in addition to KDE4.

**GNOME 2.22:** Beta 1 includes GNOME 2.22.1 [with plenty of new features and packages][2].

**YaST ported to Qt4**: openSUSE’s administration and installation tool, [YaST][3], has been ported to Qt4, providing [beautiful styling][4] for the installer, and an [improved look][5] for areas such as package management.

### Screenshots!

Here’s a quick look at openSUSE 11.0 beta 1:

<p align="center">
  <a title="New Install Theme" href="https://en.opensuse.org/Image:OS11.0beta1-inst7.png"><img src="https://news.opensuse.org/wp-content/uploads/2008/04/os110beta1-inst7_thumb.jpg" alt="os110beta1-inst7_thumb.jpg" /></a> <a title="KDE4 Desktop" href="https://en.opensuse.org/Image:OS11.0beta1-kde4-2.png"><img src="https://news.opensuse.org/wp-content/uploads/2008/04/os110beta1-kde4-2_thumb.jpg" alt="os110beta1-kde4-2_thumb.jpg" /></a>
</p>

<p align="center">
  <a title="KDE3 Desktop" href="https://en.opensuse.org/Image:OS11.0beta1-kde3.png"><img src="https://news.opensuse.org/wp-content/uploads/2008/04/os110beta1-kde3_thumb.jpg" alt="os110beta1-kde3_thumb.jpg" /></a> <a title="GNOME 2.22" href="https://en.opensuse.org/Image:OS11.0beta1-gnome.png"><img src="https://news.opensuse.org/wp-content/uploads/2008/04/os110beta1-gnome_thumb.jpg" alt="os110beta1-gnome_thumb.jpg" /></a>
</p>

<p align="center">
  For some more screenshots head over to <a href="https://en.opensuse.org/Screenshots/openSUSE_11.0_Beta1">Screenshots/openSUSE_11.0_Beta1</a> on the wiki.
</p>

### Under the Hood

**Installation in 24 minutes:** Due to changes within the installation media itself and the advances in openSUSE’s package management, an openSUSE installation is now well over 60% faster, completing in roughly just 24 minutes! (Your mileage may vary, offer not valid for 486s…)

**Other:**

  * Linux kernel 2.6.25-rc9
  * updated gcc 4.3 branch
  * libzypp 3.12.1
  * PackageKit 0.2.0
  * AppArmor 2.3
  * Xen 3.2.1 RC1
  * glibc 2.8 CVS
  * PulseAudio 0.9.10

Obsessive package watchers can find a [list of packages in Factory that’s updated daily][6]. (Just see the column labeled “Factory.”)

### Important Changes Since Alpha 3

Several important changes have happened since Alpha 3 was released, most notably:

  * Updated NetworkManager 0.7 SVN
  * RPM payload [switch to LZMA][7] (results in smaller RPM packages and faster installation of them)
  * DVD uses [images for installation][8] (speed-up)

A more detailed list of changes is available via the <a href="https://opensuse.org/Factory/News" target="_blank">Factory/News</a> page.

<!-- A sentence from Coolo -->

## Information and Download

Remember that this is a _beta_. It may not be safe to run for production systems, and should be used by users interested in testing the next release of openSUSE for bugs.

### Most Annoying Bugs

#### Live-CD

  * x86_64 live CDs do not fit on 700MB, need to be tested with DVD-R
  * Asks you to type the kernel name (on the boot prompt) which fails, just press _<return>_
  * Live-CD does not start X in VirtualBox (<a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=374710" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=374710">Bug #374710</a>) Workaround: Log in as root, run “sax2 -m 0=vesa” then “rcxdm restart”
  * Live-CD installer does not work (<a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=377565" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=377565">Bug #377565</a>, <a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=381153" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=381153">Bug #381153</a>)

<p class="editsection" style="float: right; margin-left: 5px;">
  [<a title="Bugs:Most Annoying Bugs 11.0 dev" href="https://en.opensuse.org/index.php?title=Bugs:Most_Annoying_Bugs_11.0_dev&action=edit&section=3">edit</a>]
</p>

#### DVD

  * Adding of system users is broken, see below
  * Changing something in the bootloader proposal causes broken menu.lst (<a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=380781" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=380781">Bug #380781</a>)
  * License text still from 10.3 (<span style="text-decoration: line-through;"><a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=381158" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=381158">Bug #381158</a></span>)

<p class="editsection" style="float: right; margin-left: 5px;">
  [<a title="Bugs:Most Annoying Bugs 11.0 dev" href="https://en.opensuse.org/index.php?title=Bugs:Most_Annoying_Bugs_11.0_dev&action=edit&section=4">edit</a>]
</p>

#### General

  * Patterns or patches will never be shown as selected (<a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=380356" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=380356">Bug #380356</a>)
  * GNOME Main Menu (and some other apps) are slow to respond (<a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=375701" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=375701">Bug #375701</a>) Workaround: Click on volume control in the panel, Configure local sound server then check “Enable network access to local sound devices”
  * GDM does not start, missing gdm user (<span style="text-decoration: line-through;"><a class="external text" title="https://bugzilla.novell.com/show bug.cgi?id=381227" rel="nofollow" href="https://bugzilla.novell.com/show_bug.cgi?id=381227">Bug #381227</a></span>), Fix: Reinstall gdm as below to work around
  * NVIDIA driver doesn’t compile. Workaround: check <a class="external text" title="https://lists.opensuse.org/opensuse-kde/2008-03/msg00119.html" rel="nofollow" href="https://lists.opensuse.org/opensuse-kde/2008-03/msg00119.html">here</a> for a patch.

#### Missing System Users in 11.0 Beta1

There is a Bug which affects the adding of system users in [several packages][9] on both LiveCD and DVD installation. **You have to reinstall them to get the correct users created on your system.** You can do so either in YaST or use zypper like:

`for i in aaa_base avahi beagle cups dbus-1 festival fuse \<br />
gdm hal ntp openssh PolicyKit postfix pulseaudio pwdutils \<br />
samba scrollkeeper uuid-runtime yast2-registration; \<br />
do rpm -q $i && echo zypper in -f -n $i; done`

See the [Bugs:Most\_Annoying\_Bugs\_11.0\_dev][10] page on the wiki for an up-to-date list.

### Media and Download

openSUSE 11.0 Beta 1 for i386, x86-64 and PPC comes as different media sets, all of which can be downloaded from **[https://software.opensuse.org/developer][11]**.

The next <a title="Roadmap" href="https://en.opensuse.org/Roadmap/11.0" target="_blank">planned release</a> is openSUSE 11.0 Beta 2 on May 2.

 [1]: https://www.kde.org/announcements/changelogs/changelog4_0_2to4_0_3.php
 [2]: https://library.gnome.org/misc/release-notes/2.22/
 [3]: https://opensuse.org/YaST
 [4]: https://jimmac.musichall.cz/log/?p=413
 [5]: https://duncan.mac-vicar.com/blog/archives/304
 [6]: https://distrowatch.com/table.php?distribution=suse
 [7]: https://opensuse.org/LZMA
 [8]: https://www.kdedevelopers.org/node/3385
 [9]: https://en.opensuse.org/Bugs:Most_Annoying_Bugs_11.0_dev#Missing_System_Users_in_11.0_Beta1
 [10]: https://en.opensuse.org/Bugs:Most_Annoying_Bugs_11.0_dev
 [11]: https://software.opensuse.org/developer "Download openSUSE 11.0 Beta 1"
