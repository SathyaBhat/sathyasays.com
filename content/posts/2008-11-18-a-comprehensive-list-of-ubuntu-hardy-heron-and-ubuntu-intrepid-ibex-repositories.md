---
title: A Comprehensive List of Ubuntu Hardy Heron (8.04) and Ubuntu Intrepid Ibex (8.10) Repositories
author: Bharath
type: post
date: 2008-11-18T07:09:31+00:00
url: /2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/
categories:
  - General
tags:
  - 3D
  - 8.04
  - 8.10
  - AA
  - Amarok
  - apps
  - Arch
  - AWN
  - bin
  - Brasero
  - browser
  - Canonical
  - cat
  - community
  - compiz
  - crap
  - DE
  - Debian
  - dl
  - download
  - driver
  - drivers
  - file
  - Firefox
  - flash
  - free
  - git
  - GNOME
  - Google
  - gtk
  - hardy
  - Hardy Heron
  - Heron
  - Home
  - Ibex
  - IM
  - inkscape
  - install
  - intrepid
  - Intrepid Ibex
  - KDE
  - KDE4
  - kubuntu
  - Launchpad
  - linux
  - MBR
  - media
  - Mono
  - Mozilla
  - multimedia
  - music
  - MusicBrainz
  - net
  - New
  - NVIDIA
  - Nvidia Drivers
  - Opera
  - os
  - plugin
  - preview
  - read
  - repo
  - repos
  - repositories
  - repository
  - review
  - rm
  - root
  - Screen
  - security
  - software
  - sudo
  - Super
  - support
  - sync
  - terminal
  - testing
  - Thunderbird
  - transmission
  - TV
  - Ubuntu
  - Unity
  - update
  - user
  - ux
  - Vista
  - VLC
  - vm
  - VMWare
  - warning
  - WINE
  - X
  - xp

---
Installing Linux software through repositories is the safe bet. In respect with Ubuntu, there are many software in Intrepid Ibex which I feel is crap. For eg: the &#8220;Hardware Drivers&#8221; does not have drivers for older kernels. On the other hand, there are many software (like Brasero, Transmission,Totem,VLC etc.) in Hardy that needs update, which the Hardy repositories have not provided till now. To bridge these gaps, I would like to provide you all with the repositories of Hardy and Intrepid.

**NOTE: Please think twice before installing software from other Ubuntu version repositories. It may screw up your installation**

**HARDY HERON REPOSITORIES:**

I have provided the older ones and two updates, just in case for those people who will want to install the older versions of software.
  
<!--more-->


  
SOURCES:

> \# Ubuntu supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed main restricted
> 
> \# Ubuntu community supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-updates universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-security universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-proposed universe multiverse
> 
> \# Ubuntu backports project (GPG key: 437D05B5)
  
> deb http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
  
> deb-src http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
> 
> \# CANONICAL COMMERCIAL REPOSITORY (Hosted on Canonical servers, not Ubuntu servers.
  
> \# RealPlayer10, Opera, VmWare Server and more to come.)
  
> deb http://archive.canonical.com/ubuntu hardy partner
> 
> \# UbuntuStudio Repository (GPG key: B6A4EB33)
  
> \# GPG key-file: http://archive.ubuntustudio.org/ubuntustudio.gpg
  
> deb http://archive.ubuntustudio.org/ubuntustudio hardy main
  
> deb-src http://archive.ubuntustudio.org/ubuntustudio hardy main
> 
> \## kubuntu.org packages for the latest KDE version (GPG key: DD4D5088)
  
> deb http://kubuntu.org/packages/kde-357 hardy main
  
> deb-src http://kubuntu.org/packages/kde-357 hardy main
  
> deb http://kubuntu.org/packages/kde-latest hardy main
  
> deb-src http://kubuntu.org/packages/kde-latest hardy main
> 
> \## kubuntu.org packages for the latest Koffice version (GPG key: DD4D5088)
  
> deb http://kubuntu.org/packages/koffice-latest hardy main
  
> deb-src http://kubuntu.org/packages/koffice-latest hardy main
> 
> \## kubuntu.org packages for the latest amaroK version (GPG key: DD4D5088)
  
> deb http://kubuntu.org/packages/amarok-latest hardy main
  
> deb-src http://kubuntu.org/packages/amarok-latest hardy main
> 
> \# kubuntu.org packages for KDE4 alpha-1 (GPG key: DD4D5088)
  
> deb http://kubuntu.org/packages/kde4-3.90.1 hardy main
  
> deb-src http://kubuntu.org/packages/kde4-3.90.1 hardy main
> 
> \# Bleeding edge wine packages (GPG key: 387EE263)
  
> \# GPG key-file: http://wine.budgetdedicated.com/apt/387EE263.gpg
  
> deb http://wine.budgetdedicated.com/apt hardy main
  
> deb-src http://wine.budgetdedicated.com/apt hardy main
> 
> \# Seveas&#8217; packages (GPG key: 1135D466)
  
> \# GPG key-file: http://mirror.ubuntulinux.nl/1135D466.gpg
  
> deb http://mirror.ubuntulinux.nl hardy-seveas all
  
> deb-src http://mirror.ubuntulinux.nl hardy-seveas all
> 
> \# The Opera browser (packages) (GPG key: 6A423791)
  
> deb http://deb.opera.com/opera etch non-free
> 
> \# Google picasa packages (GPG key: 7FAC5991)
  
> deb http://dl.google.com/linux/deb/ stable non-free
> 
> \# The repository from Kubuntu Germany
  
> \# GPG key-file: http://archive.czessi.net/ubuntu/kczessi.gpg
  
> deb http://archive.czessi.net/ubuntu hardy main restricted universe multiverse preview
  
> deb-src http://archive.czessi.net/ubuntu hardy main restricted universe multiverse preview
> 
> \# Achim&#8217;s Unofficial &#8216;hardy&#8217; Kubuntu packages
  
> \# GPG key-file: http://www.mpe.mpg.de/~ach/ach-gpg.asc
  
> deb http://www.mpe.mpg.de/~ach/kubuntu/hardy ./
  
> deb-src http://www.mpe.mpg.de/~ach/kubuntu/hardy ./
> 
> \# Ubuntu hardy University Klagenfurt packages
  
> \# GPG key-file: http://ubuntu.uni-klu.ac.at/uniklu-debuild.pub
  
> \# $ sudo apt-key add uniklu-debuild.pub
  
> #   uniklu:         backports and new packages
  
> #   uniklu-intern:  not freely redistributable (jvm), or modified packages
  
> #   uniklu-testing: packages not ready for general use
  
> deb http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu
  
> deb http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu-intern
  
> deb http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu-testing
  
> deb-src http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu
  
> deb-src http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu-intern
  
> deb-src http://ubuntu.uni-klu.ac.at/ubuntu.uniklu/ hardy uniklu-testing
> 
> \# MythTV Repository for Ubuntu Linux (GPG key: 80DF6D58)
  
> deb http://home.eng.iastate.edu/~superm1 hardy all
  
> deb-src http://home.eng.iastate.edu/~superm1 hardy all
> 
> \# Official Beryl Ubuntu Packages (GPG key: 1609B551)
  
> \# GPG key-file: http://ubuntu.beryl-project.org/root@lupine.me.uk.gpg
  
> deb http://ubuntu.beryl-project.org hardy main
  
> deb-src http://ubuntu.beryl-project.org hardy main
> 
> \# Ubuntu repository for Screenlets (GPG key: F854AFD7)
  
> \# GPG key-file: http://hendrik.kaju.pri.ee/ubuntu/F854AFD7.gpg
  
> deb http://hendrik.kaju.pri.ee/ubuntu hardy screenlets
  
> deb-src http://hendrik.kaju.pri.ee/ubuntu hardy screenlets
> 
> \# Subpixel Font rendering packages (GPG key: 937215FF)
  
> \# Improved fonts on LCDs &#8211; WARNING: May violate some patents
  
> \# GPG key-file: http://www.telemail.fi/mlind/ubuntu/937215FF.gpg
  
> deb http://www.telemail.fi/mlind/ubuntu hardy fonts main
  
> deb-src http://www.telemail.fi/mlind/ubuntu hardy fonts main
> 
> \## Others mlind experimental misc Packages (GPG key: 937215FF)
  
> \## GPG key-file: http://www.telemail.fi/mlind/ubuntu/937215FF.gpg
  
> deb http://www.telemail.fi/mlind/ubuntu hardy experimental
  
> deb-src http://www.telemail.fi/mlind/ubuntu hardy experimental
> 
> \# Skype packages
  
> deb http://download.skype.com/linux/repos/debian/ stable non-free
> 
> \# Geole&#8217;s Ubuntu Repository
  
> \## GPG key-file: http://www.geole.info/fileadmin/data/misc/geole.info-apt-key.gpg
  
> deb http://ubuntu.geole.info/ hardy universe multiverse
  
> deb-src http://ubuntu.geole.info/ hardy universe multiverse
  
> deb http://ubuntu.geole.info/ hardy-backports main universe multiverse restricted
  
> deb-src http://ubuntu.geole.info/ hardy-backports main universe multiverse restricted
> 
> \# Linux2Go Ubuntu Packages (GPG key: E8BDA4E3)
  
> deb http://www.linux2go.dk/ubuntu hardy main
  
> deb-src http://www.linux2go.dk/ubuntu hardy main
> 
> \# Asher256&#8217;s Repository
  
> deb http://asher256-repository.tuxfamily.org hardy main dupdate french
  
> deb http://asher256-repository.tuxfamily.org ubuntu main dupdate french
> 
> \# Tvfreeplayer Packages (GPG key: )
  
> \# GPG key-file: http://www.tvfreeplayer.com/linux/falcon/tvfreeplayer.gpg
  
> deb http://www.tvfreeplayer.com/linux/falcon hardy all
  
> deb-src http://www.tvfreeplayer.com/linux/falcon hardy all
> 
> \# gnomemeeting &#8211; ekiga (GPG key: 52ABFCB1)
  
> deb http://snapshots.ekiga.net/ubuntu/ hardy main
  
> deb-src http://snapshots.ekiga.net/ubuntu/ hardy main
> 
> \## lprod packages: many audio/video apps: avidemux, cinelerra&#8230;
  
> deb http://lprod.org/deb/hardy/ ./
  
> deb-src http://lprod.org/deb/hardy/ ./
> 
> \# Cinelerra hardy packages
  
> deb http://www.kiberpipa.org/~gandalf/ubuntu/hardy/cinelerra/i686/ ./
> 
> \# Cafuego&#8217;s hardy Stuff: Broadcom firmware, google-earth, secondlife (GPG key: 969F3F57)&#8230;
  
> deb http://au.ubuntu.cafuego.net hardy-cafuego all
  
> deb-src http://au.ubuntu.cafuego.net hardy-cafuego all
> 
> \# Debuntu Ubuntu hardy packages
  
> \# GPG Key: http://repository.debuntu.org/GPG-Key-chantra.txt
  
> deb http://repository.debuntu.org/ hardy multiverse
  
> deb-src http://repository.debuntu.org/ hardy multiverse
> 
> \# Morgoth Repository (GPG key: 7E2E4741)
  
> \# Provides Monkey&#8217;s Audio, xmms pugins, vlc plugins, gqview, audacius, audacity&#8230;
  
> \# GPG key-file: http://morgoth.free.fr/files/morgoth-signkey.gpg.asc
  
> deb http://morgoth.free.fr/ubuntu hardy-backports main
  
> deb-src http://morgoth.free.fr/ubuntu hardy-backports main
> 
> \## ATi & nVidia drivers Ubuntu packages
  
> \## GPG key: http://albertomilone.com/drivers/tseliot.asc
  
> deb http://www.albertomilone.com/drivers/hardy/latest/32bit binary/
> 
> \# edevelop &#8211; e17 (Enlightenment DR 17)
  
> \# GPG key: http://lut1n.ifrance.com/repo_key.asc
  
> deb http://edevelop.org/pkg-e/ubuntu hardy e17
  
> deb-src http://edevelop.org/pkg-e/ubuntu hardy e17
  
> deb http://e17.dunnewind.net/ubuntu hardy e17
  
> deb-src http://e17.dunnewind.net/ubuntu hardy e17
> 
> \# Musicbrainz Repository
  
> \# GPG key-file: http://ftp.musicbrainz.org/pub/musicbrainz/users/luks/public.key
  
> deb http://ftp.musicbrainz.org/pub/musicbrainz/users/luks/ubuntu hardy musicbrainz
  
> deb-src http://ftp.musicbrainz.org/pub/musicbrainz/users/luks/ubuntu hardy musicbrainz
> 
> \## Imbrandons software repository (GPG key: 887D9FD2)
  
> \## GPG key-file: http://www.imbrandon.com/packages/887D9FD2.gpg
  
> deb http://www.imbrandon.com/packages hardy all
  
> deb-src http://www.imbrandon.com/packages hardy all
> 
> \## Candyz&#8217;s Ubuntu Packages
  
> \## GPG key-file: http://cle.linux.org.tw/candyz/Ubuntu/candyz.key
  
> deb http://cle.linux.org.tw/candyz/Ubuntu/hardy i386/
> 
> \# The Ubuntu NLP Repository (GPG key: 8ABD1965)
  
> \# GPG key-file: http://cl.naist.jp/~eric-n/ubuntu-nlp/8ABD1965.gpg
  
> deb http://cl.naist.jp/~eric-n/ubuntu-nlp hardy all
  
> deb-src http://cl.naist.jp/~eric-n/ubuntu-nlp hardy all
> 
> \# Ubuntu System Administrator packages (GPG key: 2F306651)
  
> \# GPG key-file: http://ubuntu.moshen.de/2F306651.gpg
  
> deb http://ubuntu.moshen.de hardy multimedia misc
  
> deb-src http://ubuntu.moshen.de hardy multimedia misc
> 
> \## Michael Biebl Tracker Repository (GPG key: BD058554)
  
> \## GPG Key-file: http://www.teco.edu/~biebl/biebl.asc
  
> deb http://debs.michaelbiebl.de/ hardy main
  
> deb-src http://debs.michaelbiebl.de/ hardy main
> 
> \# The Consciousness Repository (GPG key: DD385D79)
  
> \# GPG key-file: http://debs.peadrop.com/DD385D79.gpg
  
> deb http://debs.peadrop.com hardy all
  
> deb-src http://debs.peadrop.com hardy all
> 
> \## Tolero Ubuntu Repository
  
> deb http://ubuntu.tolero.org/ hardy main
  
> deb-src http://ubuntu.tolero.org/ hardy main
> 
> \# IVTV Repository for Ubuntu Linux (GPG key: 80DF6D58)
  
> \# GPG key-file: http://dl.ivtvdriver.org/ubuntu/80DF6D58.gpg
  
> deb http://dl.ivtvdriver.org/ubuntu hardy all
  
> deb-src http://dl.ivtvdriver.org/ubuntu hardy all
> 
> \# syzygy42 repository: avant-window-navigator, exaile, closure&#8230; (GPG key: 8434D43A)
  
> \# GPG key-file: http://download.tuxfamily.org/syzygy42/8434D43A.gpg
  
> deb http://download.tuxfamily.org/syzygy42/ hardy all
  
> deb-src http://download.tuxfamily.org/syzygy42/ hardy all
> 
> \## Firefox 3.0 alpha builds for hardy (unstable)
  
> deb-src http://gnomefreak.youmortals.com/mozilla-testing hardy main
> 
> \## Swiftfox (enhanced Firefox for linux) packages
  
> deb http://getswiftfox.com/builds/debian unstable non-free
> 
> \# Sonnes repository (aMule AdunanZa, Audacious)
  
> deb http://adurepo.altervista.org/ubuntu hardy all
  
> deb-src http://adurepo.altervista.org/ubuntu hardy all
> 
> \# darkmagez repository: rhythmbox and newer gtk (GPG key: A3012FB3)
  
> \# GPG key-file: http://mirror.randumb.org/darkmagez/repo/A3012FB3.gpg
  
> deb http://mirror.randumb.org/darkmagez/repo hardy-darkmagez multimedia-experimental #core-experimental
  
> deb-src http://mirror.randumb.org/darkmagez/repo hardy-darkmagez multimedia-experimental #core-experimental
> 
> \## Raof Repository: newer versions of Compiz, beagle, mono, scribus&#8230; (GPG key: 2F306651)
  
> \## GPG key-file: http://raof.dyndns.org/falcon/2F306651.gpg
  
> ##deb http://raof.dyndns.org/falcon hardy all
  
> deb-src http://raof.dyndns.org/falcon hardy all
> 
> \# FoLKeN &#8216;Repozytorium&#8217; (GPG key: 6FB65A0F)
  
> deb http://deb.svx.pl/ hardy main universe bleeding
  
> deb-src http://deb.svx.pl/ hardy main universe bleeding
> 
> \# Le dépomaniak repository (GPG key: 1D59E694)
  
> \# GPG key-file: http://ubuntu.davromaniak.eu/1D59E694.gpg
  
> deb http://ubuntu.davromaniak.eu hardy-depomaniak all
  
> deb-src http://ubuntu.davromaniak.eu hardy-depomaniak all
> 
> \# Mez&#8217;s Repository (GPG key: 6AAAA569)
  
> \# GPG key-file: http://apt.sourceguru.net/6AAAA569.gpg
  
> deb http://apt.sourceguru.net hardy all
  
> deb-src http://apt.sourceguru.net hardy all
> 
> \# Ryan Kavanagh&#8217;s packages (GPG key: 02544D0E)
  
> \# GPG key-file: http://packages.ryanak.ca/02544D0E.gpg
  
> deb http://packages.ryanak.ca ryan-hardy all
  
> deb-src http://packages.ryanak.ca ryan-hardy all
> 
> \# OpenedHand Debian/Ubuntu Packages
  
> deb http://debian.o-hand.com hardy/
  
> deb-src http://debian.o-hand.com hardy/
> 
> \# OpenSync svn ubuntu repository (GPG key: B029CB84)
  
> deb http://www.in.fh-merseburg.de/~jahn/opensync-0.21/ hardy main
  
> deb-src http://www.in.fh-merseburg.de/~jahn/opensync-0.21/ hardy main
> 
> \# Iuculano&#8217;s debian packages (GPG key: AE3BE9AA)
  
> \# GPG key-file: http://ubuntu.iuculano.it/AE3BE9AA.gpg
  
> deb http://ubuntu.iuculano.it hardy amsn thunderbird #ck-kernel #all
  
> deb-src http://ubuntu.iuculano.it hardy amsn thunderbird #ck-kernel #all
> 
> \# Elisa Debian Packages
  
> deb http://elisa.fluendo.com/packages hardy main
> 
> \# PollyCooke, il repository
  
> deb http://download.tuxfamily.org/pollyrepo hardy/
> 
> \# Treviño&#8217;s Ubuntu hardy Fawn Repository (GPG key: 81836EBF &#8211; DD800CD9)
  
> \# Many &#8220;random&#8221; bleeding edge software: aMule, aMSN, Mercury, flash&#8230;
  
> \# Further informations and complete packages list: http://3v1n0.tuxfamily.org
  
> deb http://download.tuxfamily.org/3v1deb hardy 3v1n0
  
> deb-src http://download.tuxfamily.org/3v1deb hardy 3v1n0
> 
> \# Treviño&#8217;s Ubuntu hardy EyeCandy Repository (GPG key: 81836EBF &#8211; DD800CD9)
  
> \# Many eyecandy 3D apps like Beryl, compiz and kiba-dock snapshots
  
> \# built using latest available (working) sources from git/svn/cvs&#8230;
  
> deb http://download.tuxfamily.org/3v1deb hardy eyecandy
  
> deb-src http://download.tuxfamily.org/3v1deb hardy eyecandy
> 
> \## Treviño&#8217;s Ubuntu Suspend2 patched kernels Repository (GPG key: 81836EBF &#8211; DD800CD9)
  
> \## Ubuntu kernels patched with Suspend2 plus other related tools www.suspend2.net
  
> \## Warning: they will replace standard ubuntu kernel related packages
  
> deb http://download.tuxfamily.org/3v1deb hardy suspend2
  
> deb-src http://download.tuxfamily.org/3v1deb hardy suspend2
  
> deb http://ftp.osuosl.org/pub/pculture.org/miro/linux/repositories/ubuntu hardy/
  
> deb http://gnomefreak.youmortals.com/mozilla-testing hardy main
  
> deb-src http://gnomefreak.youmortals.com/mozilla-testing hardy main
  
> deb http://ubuntu.cafuego.net hardy-cafuego media
> 
> deb http://archive.ubuntu.com/ubuntu/ hardy-backports restricted main multiverse universe
  
> deb http://dl.google.com/linux/deb/ testing non-free
  
> deb http://ppa.launchpad.net/kubuntu-members-kde4/ubuntu hardy main
  
> deb http://getswiftfox.com/builds/debian unstable non-free
  
> deb http://archive.canonical.com/ubuntu hardy partner
  
> deb http://ppa.launchpad.net/do-core/ubuntu hardy main
  
> deb http://download.tuxfamily.org/3v1deb hardy eyecandy
  
> deb http://download.tuxfamily.org/3vldeb edgy beryl-svn
  
> deb http://ppa.launchpad.net/gilir/ubuntu hardy main universe
  
> deb http://ppa.launchpad.net/mvo/ubuntu hardy main
  
> deb http://archive.ubuntustudio.org/ubuntustudio feisty main
> 
> UPDATE 1:
> 
> \# Ubuntu supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed main restricted
> 
> \# Ubuntu community supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-updates universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-security universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-proposed universe multiverse
> 
> \# Ubuntu backports project (GPG key: 437D05B5)
  
> deb http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
  
> deb-src http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
> 
> \# Bleeding edge wine packages (GPG key: 387EE263)
  
> \# GPG key-file: http://wine.budgetdedicated.com/apt/387EE263.gpg
  
> deb http://wine.budgetdedicated.com/apt hardy main
  
> deb-src http://wine.budgetdedicated.com/apt hardy main
> 
> \# The Opera browser (packages) (GPG key: 6A423791)
  
> deb http://deb.opera.com/opera etch non-free
> 
> \# Google picasa packages (GPG key: 7FAC5991)
  
> deb http://dl.google.com/linux/deb/ stable non-free
> 
> \# Skype packages
  
> deb http://download.skype.com/linux/repos/debian/ stable non-free
> 
> \# Geole&#8217;s Ubuntu Repository
  
> \## GPG key-file: http://www.geole.info/fileadmin/data/misc/geole.info-apt-key.gpg
  
> deb http://debian.geole.info/ etch main contrib non-free
  
> deb-src http://debian.geole.info/ etch main contrib non-free
  
> deb http://debian.geole.info/ etch-backports main contrib non-free
  
> deb-src http://debian.geole.info/ etch-backports main contrib non-free
> 
> \# Asher256&#8217;s Repository
  
> deb http://asher256-repository.tuxfamily.org ubuntu french
> 
> \# gnomemeeting &#8211; ekiga (GPG key: 52ABFCB1)
  
> deb http://snapshots.ekiga.net/debian/ sid main
> 
> \## lprod packages: many audio/video apps: avidemux, cinelerra&#8230;
  
> deb http://lprod.org/deb/hardy/ ./
  
> deb-src http://lprod.org/deb/hardy/ ./
> 
> \# Morgoth Repository (GPG key: 7E2E4741)
  
> \# Provides Monkey&#8217;s Audio, xmms pugins, vlc plugins, gqview, audacius, audacity&#8230;
  
> \# GPG key-file: http://morgoth.free.fr/files/morgoth-signkey.gpg.asc
  
> deb http://morgoth.free.fr/ubuntu hardy-backports main
  
> deb-src http://morgoth.free.fr/ubuntu hardy-backports main
> 
> \# edevelop &#8211; e17 (Enlightenment DR 17)
  
> \# GPG key: http://lut1n.ifrance.com/repo_key.asc
  
> deb http://e17.dunnewind.net/ubuntu hardy e17
  
> deb-src http://e17.dunnewind.net/ubuntu hardy e17
> 
> \# The Ubuntu NLP Repository (GPG key: 8ABD1965)
  
> \# GPG key-file: http://cl.naist.jp/~eric-n/ubuntu-nlp/8ABD1965.gpg
  
> deb http://cl.naist.jp/~eric-n/ubuntu-nlp hardy all
  
> deb-src http://cl.naist.jp/~eric-n/ubuntu-nlp hardy all
> 
> \# Le dépomaniak repository (GPG key: 1D59E694)
  
> \# GPG key-file: http://ubuntu.davromaniak.eu/1D59E694.gpg
  
> deb http://ubuntu.davromaniak.eu hardy-depomaniak all
  
> deb-src http://ubuntu.davromaniak.eu hardy-depomaniak all
> 
> \# Treviño&#8217;s Ubuntu hardy Fawn Repository (GPG key: 81836EBF &#8211; DD800CD9)
  
> \# Many &#8220;random&#8221; bleeding edge software: aMule, aMSN, Mercury, flash&#8230;
  
> \# Further informations and complete packages list: http://3v1n0.tuxfamily.org
  
> deb http://download.tuxfamily.org/3v1deb feisty 3v1n0
  
> deb-src http://download.tuxfamily.org/3v1deb feisty 3v1n0
> 
> \## Treviño&#8217;s Ubuntu Suspend2 patched kernels Repository (GPG key: 81836EBF &#8211; DD800CD9)
  
> \## Ubuntu kernels patched with Suspend2 plus other related tools www.suspend2.net
  
> \## Warning: they will replace standard ubuntu kernel related packages
  
> deb http://download.tuxfamily.org/3v1deb feisty suspend2
  
> deb http://ftp.osuosl.org/pub/pculture.org/miro/linux/repositories/ubuntu feisty/
> 
> deb http://archive.ubuntu.com/ubuntu/ hardy-backports restricted main multiverse universe
  
> deb http://dl.google.com/linux/deb/ testing non-free
  
> deb http://ppa.launchpad.net/kubuntu-members-kde4/ubuntu hardy main
  
> deb http://getswiftfox.com/builds/debian unstable non-free
  
> deb http://archive.canonical.com/ubuntu hardy partner
  
> deb http://ppa.launchpad.net/do-core/ubuntu hardy main
  
> deb http://ppa.launchpad.net/gilir/ubuntu hardy main universe
  
> deb http://ppa.launchpad.net/mvo/ubuntu hardy main
  
> \## key AF425CB5
  
> deb http://us.ubuntu.cafuego.net hardy-cafuego all b43 google inkscape internode rtorrent secondlife
  
> deb http://e17.dunnewind.net/ubuntu gutsy e17
  
> deb http://download.tuxfamily.org/geubuntu/ gutsy/
> 
> UPDATE 2:
> 
> \# Ubuntu supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security main restricted
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed main restricted
> 
> \# Ubuntu community supported packages (GPG key: 437D05B5)
  
> deb http://archive.ubuntu.com/ubuntu/ hardy universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-updates universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-security universe multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ hardy-proposed universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-updates universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-security universe multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu hardy-proposed universe multiverse
> 
> \# Ubuntu backports project (GPG key: 437D05B5)
  
> deb http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
  
> deb-src http://mi.mirror.garr.it/ubuntu hardy-backports main restricted universe multiverse
> 
> \# Bleeding edge wine packages (GPG key: 387EE263)
  
> \# GPG key-file: http://wine.budgetdedicated.com/apt/387EE263.gpg
  
> deb http://wine.budgetdedicated.com/apt hardy main
  
> deb-src http://wine.budgetdedicated.com/apt hardy main
> 
> \# The Opera browser (packages) (GPG key: 6A423791)
  
> deb http://deb.opera.com/opera etch non-free
> 
> \# Google picasa packages (GPG key: 7FAC5991)
  
> deb http://dl.google.com/linux/deb/ stable non-free
> 
> \# Skype packages
  
> deb http://download.skype.com/linux/repos/debian/ stable non-free
> 
> \# Geole&#8217;s Ubuntu Repository
  
> \## to get the key &#8211; in terminal type: sudo aptitude install geole-keyring
  
> deb http://debian.geole.info/ etch main contrib non-free
  
> deb-src http://debian.geole.info/ etch main contrib non-free
  
> deb http://debian.geole.info/ etch-backports main contrib non-free
  
> deb-src http://debian.geole.info/ etch-backports main contrib non-free
> 
> \# Asher256&#8217;s Repository
  
> deb http://asher256-repository.tuxfamily.org ubuntu french
> 
> \# gnomemeeting &#8211; ekiga (GPG key: 52ABFCB1)
  
> deb http://snapshots.ekiga.net/snapshots/ubuntu/ hardy main

**EDIT:** Thanks to <span class="post-author vcard"><span class="fn">Anatoly for <a href="http://mathpages.blogspot.com/2008/04/ubuntu-hardy-repositories-list.html">this post</a>.  Also I would like to advice that please do not risk adding and/or installing from the testing and unstable repositories. It may screw up your working system<br /> </span></span>

\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___\___

**INTREPID IBEX REPOSITORIES :**

> deb http://security.ubuntu.com/ubuntu intrepid-security main restricted
  
> deb-src http://security.ubuntu.com/ubuntu intrepid-security restricted main multiverse universe #Added by software-properties
  
> deb http://security.ubuntu.com/ubuntu intrepid-security universe
  
> deb http://security.ubuntu.com/ubuntu intrepid-security multiverse
  
> deb http://archive.ubuntu.com/ubuntu/ intrepid main universe restricted multiverse
  
> deb-src http://archive.ubuntu.com/ubuntu/ intrepid main universe restricted multiverse #Added by software-properties
  
> deb http://archive.ubuntu.com/ubuntu/ intrepid-updates universe main multiverse restricted
  
> deb-src http://archive.ubuntu.com/ubuntu/ intrepid-updates universe main multiverse restricted #Added by software-properties
  
> deb http://archive.ubuntu.com/ubuntu/ intrepid-proposed universe main multiverse restricted
  
> deb-src http://archive.ubuntu.com/ubuntu/ intrepid-proposed universe main multiverse restricted #Added by software-properties
  
> deb http://archive.ubuntu.com/ubuntu/ intrepid-backports universe main multiverse restricted
  
> deb-src http://archive.ubuntu.com/ubuntu/ intrepid-backports universe main multiverse restricted #Added by software-properties
  
> deb http://archive.canonical.com/ubuntu intrepid partner
  
> deb-src http://archive.canonical.com/ubuntu intrepid partner
  
> deb http://packages.medibuntu.org/ intrepid free non-free
  
> deb-src http://packages.medibuntu.org/ intrepid free non-free
  
> #deluge-torrent
  
> deb http://ppa.launchpad.net/deluge-team/ubuntu intrepid main restricted universe multiverse
  
> deb-src http://ppa.launchpad.net/deluge-team/ubuntu intrepid main restricted universe multiverse
  
> #empathy
  
> deb http://ppa.launchpad.net/telepathy/ubuntu intrepid main
  
> deb-src http://ppa.launchpad.net/telepathy/ubuntu intrepid main
  
> deb http://ppa.launchpad.net/exaile-devel/ubuntu intrepid main

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-568" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-568" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-568" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>