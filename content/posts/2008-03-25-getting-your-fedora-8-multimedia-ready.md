---
title: Getting your Fedora 8 Multimedia Ready
author: Sathya
type: post
date: 2008-03-25T08:14:46+00:00
url: /2008/03/25/getting-your-fedora-8-multimedia-ready/
categories:
  - News
tags:
  - 1-click install
  - Adobe
  - applications
  - Arch
  - cat
  - codecs
  - commands
  - DE
  - download
  - DVD
  - Fedora
  - file
  - flash
  - free
  - how-tos
  - IM
  - install
  - linux
  - Livna
  - media
  - move
  - Mozilla
  - Mplayer
  - multimedia
  - openSuSE
  - Opera
  - plugin
  - read
  - repo
  - rm
  - root
  - rpm
  - Sun
  - SUSE
  - switch
  - terminal
  - tutorials
  - ux
  - VLC
  - w32 codecs
  - X
  - yum

---
Unlike openSUSE 10.3, Fedora doesnt have the 1-click installers for easy install of codecs ,so you&#8217;ll have to rely on Terminal and Yum to get it up and running.

All the below operations require Root privileges, so switch to root first by opening the Terminal and typing

All commands under &#8220;code&#8221; will have to be entered at the terminal

> `su root`

Step 1. Add Livna repo

> `wget rpm.livna.org/livna-release-8.rpm<br />
rpm -ivh livna-release-8.rpm`

Step2. Add the Macromedia Repo

> `wget linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm<br />
rpm -ivh adobe-release-i386-1.0-1.noarch.rpm`

Step 3:  Install Multimedia Applications

> `yum -y remove totem totem-mozplugin<br />
yum -y install totem-xine totem-xine-mozplugin libdvdcss libdvdread libdvdplay livdvdnav lsdvd xine-lib-extras-nonfree libdvdcss libdvdread libdvdplay flash-plugin libquicktime gstreamer-plugins-ugly gstreamer-plugins-bad<br />
` 

Step 4: Install w32Codecs in order to play everything under the Sun.

> `wget www1.mplayerhq.hu/MPlayer/releases/codecs/mplayer-codecs-20061022-1.i386.rpm<br />
rpm -ivh mplayer-codecs-20061022-1.i386.rpm<br />
wget www1.mplayerhq.hu/MPlayer/releases/codecs/mplayer-codecs-extra-20061022-1.i386.rpm<br />
rpm -ivh mplayer-codecs-extra-20061022-1.i386.rpm`

(optional) Install VLC

> `yum install vlc<br />
yum install python-vlc mozilla-vlc`

That&#8217;s it! you can use Totem or VLC to play them video/audio files! Have a blast!