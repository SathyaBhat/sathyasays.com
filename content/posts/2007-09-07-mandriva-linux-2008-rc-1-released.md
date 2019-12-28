---
title: Mandriva Linux 2008 RC 1 Released
author: Sathya
type: post
date: 2007-09-07T17:36:19+00:00
url: /2007/09/07/mandriva-linux-2008-rc-1-released/
categories:
  - News
tags:
  - /dev
  - 3D
  - ALSA
  - Apple
  - applications
  - Arch
  - beta
  - bin
  - browser
  - cat
  - chipset
  - codecs
  - community
  - compiz
  - compiz fusion
  - console
  - cover
  - DE
  - Desktop
  - desktop environment
  - desktop environments
  - dl
  - driver
  - drivers
  - dual
  - DVD
  - exe
  - file
  - free
  - free software
  - fun
  - fusion
  - GNOME
  - guide
  - IM
  - images
  - install
  - iso
  - KDE
  - KHTML
  - laptop
  - linux
  - MBR
  - menu
  - Microsoft
  - mount
  - move
  - nepomuk
  - net
  - New
  - notes
  - open source
  - os
  - plugin
  - preview
  - Qt
  - read
  - repo
  - repos
  - repository
  - review
  - rm
  - RMS
  - script
  - software
  - Sun
  - Super
  - support
  - tar
  - theme
  - themes
  - TV
  - Unity
  - update
  - user
  - ux
  - Wireless
  - write
  - X
  - xp
  - XRAndR

---
The first release candidate of Mandriva Linux 2008, codenamed Galilee, [is now available][1]. The [release notes][2] are also available via the wiki. A guide to [major new features][3] (some of which are not yet implemented in this release candidate), and the [detailed technical specifications][4] are also available. This release candidate is available as a three CD or one DVD Free edition (containing no non-free software or drivers) for the x86-32 and x86-64 architectures, with a traditional installer, and as a mini-CD edition for both x86-32 and x86-64 architectures. A One combined live / install CD edition will be released in the near future (problems with unionfs prevented the One edition from being release at the same time as the other editions).

Updated Software:

##  <span class="mw-headline">GNOME 2.20 </span>

Once again, Mandriva Linux 2008 will come with the latest release of <a href="https://www.gnome.org/" class="external text" title="https://www.gnome.org" rel="nofollow">GNOME</a>, which will be hot off the press at release time. The development releases will feature the latest available releases of GNOME 2.19, the development series for 2.20. New features planned for GNOME 2.20 include:

  * A new Appearance configuration applet merging the old Themes, Font and Background applets
  * <a href="https://ekiga.org/" class="external text" title="https://ekiga.org" rel="nofollow">Ekiga</a> 3.0, featuring a plugin framework for audio and video codecs, a revised interface, and SIP presence support
  * Support for fillable forms in <a href="https://www.gnome.org/projects/evince/" class="external text" title="https://www.gnome.org/projects/evince/" rel="nofollow">Evince</a>, the GNOME PDF reader
  * <a href="https://www.gnome.org/projects/evolution/" class="external text" title="https://www.gnome.org/projects/evolution/" rel="nofollow">Evolution</a> <a href="https://www.go-evolution.org/Evo2.12" class="external text" title="https://www.go-evolution.org/Evo2.12" rel="nofollow">2.12</a>, with better spam filtering and Microsoft Exchange support

See the full plan <a href="https://live.gnome.org/RoadMap" class="external text" title="https://live.gnome.org/RoadMap" rel="nofollow">here</a>.

<a name="KDE_3.5.7"></a>

## <span class="editsection"></span> <span class="mw-headline">KDE 3.5.7 </span>

The latest stable KDE 3 release will be included, with all the bug fixes since the previous 3.5.6 release. KDE 3.5.7 is mainly a maintenance release but also comes with some new features :

  * Improved KAddressBook, KOrganizer or KAlarm
  * Kmail is new able to manage IMAP quotas and can use custom templates for creating, replying or forwarding messages
  * KPDF is able to display more complex PDF files than before
  * UML modeler Umbrello can generate C#-style code and now supports Java 5 generics
  * Kdevelop has better autocompletion and now supports Qt4.
  * KHTML and KJS engine (managing HTML rendering and Javascript execution) have been improved. For instance, the mouse pointer now has a different icon if a link is opening in a new window or not.

<a name="KDE_4_preview"></a>

## <span class="editsection"></span> <span class="mw-headline">KDE 4 preview </span>

KDE 4 will be available as an experimental preview, with the latest available pre-release included. The development releases will be tracking KDE 4 development very closely. The changes in KDE 4 are countless and, of course, include the revolutionary <a href="https://nepomuk.semanticdesktop.org/" class="external text" title="https://nepomuk.semanticdesktop.org" rel="nofollow">Nepomuk semantic desktop system</a>, whose development is being led by Mandriva. There is no single resource for a full list of new features in KDE 4, but <a href="https://en.wikipedia.org/wiki/KDE_4" class="external text" title="https://en.wikipedia.org/wiki/KDE_4" rel="nofollow">Wikipedia</a> gives a good overview.

<a name="XFCE_4.4.1"></a>

## <span class="editsection"></span> <span class="mw-headline">XFCE 4.4.1 </span>

The new Mandriva [XFCE development community][5] will present improved packages for XFCE 4.4.1 in Mandriva Linux 2008. They are working on various areas including integration of the Mandriva themes and menu structure into the XFCE desktop. XFCE will be moved into the supported <span style="font-family: courier; color: blue; font-style: italic">/main</span> repository, and we hope to build an XFCE-based Mandriva Linux One image for 2008 in addition to the regular GNOME- and KDE-based One images.

<a name="Kernel_2.6.22"></a>

## <span class="editsection"></span> <span class="mw-headline">Kernel 2.6.22 </span>

As Mandriva Linux 2008 marks a new basesystem (after the previous basesystem was used for Mandriva Linux 2007 and 2007 Spring), it will of course include a new kernel. 2.6.22 will add support for new hardware and also has many interesting new features.

Perhaps the biggest new feature visible to end users will be the new Devicescape (mac80211) wireless networking stack, which provides a superior base with much more common code than the previous kernel wireless stack, allowing drivers to be more reliable and functional.

2.6.22 also includes the new &#8216;tickless&#8217; technology which will save battery power on laptops, with the effect increasing over time as applications are improved to avoid needlessly waking up the kernel. There&#8217;s a good write-up of this system <a href="https://news.zdnet.com/2100-3513_22-6192865.html" class="external text" title="https://news.zdnet.com/2100-3513_22-6192865.html" rel="nofollow">here</a>.

It also includes <a href="https://www.alsa-project.org/" class="external text" title="https://www.alsa-project.org" rel="nofollow">ALSA</a> 1.0.14, adding support for some newer sound cards and chipsets and improving support for others.

Other improvements include the usual gradual improvements to suspend support, a new scheduler (which will result in improved responsiveness in typical desktop use), and the integration of the <a href="https://ivtvdriver.org/" class="external text" title="https://ivtvdriver.org" rel="nofollow">ivtv</a> TV card driver (as used, notably, for the Hauppauge PVR series cards). An exhaustive overview of changes between 2.6.21 and 2.6.22 is available <a href="https://kernelnewbies.org/Linux_2_6_22" class="external text" title="https://kernelnewbies.org/Linux_2_6_22" rel="nofollow">here</a>: the same site has similar pages covering the changes back to 2.6.17, the kernel that was included in Mandriva Linux 2007 Spring.

<a name="Compiz_Fusion"></a>

## <span class="editsection"></span> <span class="mw-headline">Compiz Fusion </span>

Compiz Fusion, the result of the re-merge between the Compiz and Beryl 3D desktop technologies, will replace Compiz and Beryl in Mandriva Linux 2008. The development branch is currently tracking the pre-release Fusion code, prior to the first official release. New features in Fusion are many, and a video demonstrating some of them is available at <a href="https://www.youtube.com/watch?v=E4Fbk52Mk1w" class="external text" title="https://www.youtube.com/watch?v=E4Fbk52Mk1w" rel="nofollow">YouTube</a>.

<a name="Other_significant_updates"></a>

## <span class="editsection"></span> <span class="mw-headline">Other significant updates </span>

Other significant updates will include <a href="https://www.x.org/wiki/Releases/7.3" class="external text" title="https://www.x.org/wiki/Releases/7.3" rel="nofollow">X.org 7.3</a>, featuring the new XrandR 1.2 framework which vastly improves support for multiple displays and display hotplugging on supported drivers, <a href="https://www.openoffice.org/" class="external text" title="https://www.openoffice.org/" rel="nofollow">OpenOffice.org</a> <a href="https://www.openoffice.org/press/press_release_ooo2.2.0.html" class="external text" title="https://www.openoffice.org/press/press_release_ooo2.2.0.html" rel="nofollow">2.2</a>, featuring improved text rendering, improved PDF exporting and enhanced compatibility with Excel spreadsheets, <a href="https://gcc.gnu.org/" class="external text" title="https://gcc.gnu.org" rel="nofollow">GCC</a> <a href="https://gcc.gnu.org/gcc-4.2/changes.html" class="external text" title="https://gcc.gnu.org/gcc-4.2/changes.html" rel="nofollow">4.2</a> (with a complementary build of <a href="https://gcc.gnu.org/gcc-4.3/changes.html" class="external text" title="https://gcc.gnu.org/gcc-4.3/changes.html" rel="nofollow">4.3</a> available as an option in the <span style="font-family: courier; color: blue; font-style: italic">/main</span> repository) and <a href="https://icedtea.classpath.org/" class="external text" title="https://icedtea.classpath.org" rel="nofollow">IcedTea</a>, a GNU project which makes it possible to provide an open source Java implementation based on the code open sourced by Sun as the <a href="https://openjdk.java.net/" class="external text" title="https://openjdk.java.net/" rel="nofollow">OpenJDK</a> project. IcedTea will likely not be ready for use as a browser plugin by the time of 2008&#8217;s release.

## <span class="mw-headline">Changes from previous betas</span>

Changes from previous beta releases include:

<a name="Draknetcenter"></a>

### <span class="editsection"></span><span class="mw-headline">Draknetcenter</span>

<span style="font-family: courier; color: blue">draknetcenter</span>, the new consolidated network configuration and monitoring tool, is included in this release candidate. For now it is available only by running <span style="font-family: courier; color: #7a4707; background-color: #e8e8e8">draknetcenter</span> from a console or a run dialog. This tool is still undergoing revision and improvement: the version you see in this release candidate is not the final design.

<a name="New_menu_structure"></a>

### <span class="editsection"></span> <span class="mw-headline">New menu structure</span>

A new menu structure, based on an initial proposal by Frederik Himpe, has been implemented in this release candidate. This structure attempts to reduce the amount of nesting in the menus. Applications are split into category groups. In each category group, applications native to the current desktop environment are displayed in the top level, and applications native to other desktop environments are displayed in a sub level. Some applications that are commonly used across many desktop environments are specially configured to always appear in the top level.

<a name="Kernel_changes"></a>

### <span class="editsection"></span><span class="mw-headline">Kernel changes</span>

The <span style="color: #7a0a7f">kernel</span> package has now adopted the <span style="color: #7a0a7f">kernel-tmb</span> spec file, which means that the kernel packages have been renamed. The old <span style="color: #7a0a7f">kernel</span> is now <span style="color: #7a0a7f">kernel-desktop</span>. The old <span style="color: #7a0a7f">kernel-enterprise</span> is now <span style="color: #7a0a7f">kernel-server</span>. The old <span style="color: #7a0a7f">kernel-legacy</span> is now <span style="color: #7a0a7f">kernel-desktop586</span>. A <span style="color: #7a0a7f">kernel-laptop</span> package is now introduced, which contains several customizations useful to laptops in terms of reducing power usage.

This also means that the official <span style="color: #7a0a7f">kernel</span> packages now adopt the <span style="color: #7a0a7f">kernel-tmb</span> style for source and headers. Each kernel package now has its own <span style="color: #7a0a7f">-devel</span> package &#8211; e.g. <span style="color: #7a0a7f">kernel-desktop586-devel</span> &#8211; which contains the source and headers necessary for building external kernel modules. This is the package you should install if you need to compile external kernel modules. The single <span style="color: #7a0a7f">kernel-source</span> package is of interest only to those who need to build an application against a complete copy of the kernel source, or those interested in building their own kernels.

<a name="Availability"></a>

## <span class="editsection"></span><span class="mw-headline">Availability</span>

This release candidate is available as a Free edition for the x86-32 and x86-64 architectures, on three CDs or one DVD, with a traditional installer. It is also available in a mini CD edition for both x86-32 and x86-64 architectures. It will also be available as a One combined live / install CD edition in the near future: issues with unionfs prevented the One edition from being released at the same time as the other editions.

The images are available from any official Mandriva mirror site in the /devel/iso/2008.0 subdirectory. For the list of Mandriva mirrors see [CookerMirrors][6].

 [1]: https://wiki.mandriva.com/en/Releases/Mandriva/2008.0/Development/RC1
 [2]: https://wiki.mandriva.com/en/Releases/Mandriva/2008.0/Notes
 [3]: https://wiki.mandriva.com/en/Releases/Mandriva/2008.0/What%27s_New
 [4]: https://wiki.mandriva.com/en/Development/Ideas/Technical_specs_2008
 [5]: https://wiki.mandriva.com/en/Development/Ideas/XFCE "Development/Ideas/XFCE"
 [6]: https://wiki.mandriva.com/en/CookerMirrors "CookerMirrors"
