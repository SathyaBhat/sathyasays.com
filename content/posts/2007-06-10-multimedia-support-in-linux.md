---
title: Multimedia support in Linux
author: Sathya
type: post
date: 2007-06-10T14:29:26+00:00
url: /2007/06/10/multimedia-support-in-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - '*buntu'
  - 1-click install
  - Adobe
  - Amarok
  - applications
  - Arch
  - AWN
  - cat
  - codecs
  - DE
  - Debian
  - dl
  - download
  - DVD
  - Fedora
  - file
  - flash
  - free
  - GNOME
  - IM
  - indic
  - install
  - KDE
  - kubuntu
  - linux
  - Livna
  - media
  - move
  - Mozilla
  - Mplayer
  - multimedia
  - open source
  - openSuSE
  - Opera
  - os
  - plugin
  - read
  - repo
  - rm
  - root
  - rpm
  - Screen
  - Sun
  - support
  - SUSE
  - switch
  - terminal
  - tutorials
  - Ubuntu
  - unable
  - user
  - ux
  - VLC
  - X
  - yum

---
One of the most common complaints about Linux is that users are unable to play common media files such as mp3&#8217;s etc. This is mainly due to Copyright Restrictions, which prohibit bundling of the required codecs. The following steps indicate how to get those mp3s of yours blasting:

### For *buntu Users:

Well it pretty simple, All you&#8217;ve to do it click on Add/Remove Programs and choose &#8220;Ubuntu Restricted Extras&#8221;. The snapshot below indicates the package under Kubuntu Feisty Fawn.

<p align="center">
  <a title="Adept" href="https://i1.wp.com/sathyasays.wordpress.com/files/2007/06/adept.png"><img src="https://i1.wp.com/sathyasays.wordpress.com/files/2007/06/adept.thumbnail.png?w=740" alt="Adept" data-recalc-dims="1" /></a>
</p>

### For Debian users:

Have a look at [this][1] post

### For OpenSUSE users:

First, get the Restricted Format 1-click installer. Here&#8217;s the links:

  * [For KDE Users][2]
  * [For GNOME users][3]

This will enable you to have:

  * Flash
  * Java
  * Latest Amarok (with MP3 Support) for KDE, or Helix-Banshee for GNOME users
  * Encrypted DVD (_libdvdcss_)
  * Extra xine codecs, for MPEG-4 etc. (_libxine1_)
  * K3b with MP3 Support (_k3b-codecs_)
  * Win 32 Codecs (_w32codec-all_)

..as well as the option of installing many more applications (**select _Advanced_ mode at the screen**), including:

  * Opera
  * KMPlayer
  * Kplayer
  * MPlayer
  * Azureus
  * VLC
  * Codeine
  * ..and more

If you skipped installing VLC, then fear not! Install VLC via the 1-Click installer! [Here&#8217;s][4] the link.

That&#8217;s it!

### For Fedora users

All the below operations require Root privileges, so switch to root first by opening the Terminal and typing

`su root`

Step 1. Add Livna repo

> `wget rpm.livna.org/livna-release-8.rpm`
  
> `rpm -ivh livna-release-8.rpm`

Step2. Add the Macromedia Repo

> `wget http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm`
  
> `rpm -ivh adobe-release-i386-1.0-1.noarch.rpm`

Step 3:  Install Multimedia Applications

> `yum -y remove totem totem-mozplugin<br />
yum -y install totem-xine totem-xine-mozplugin libdvdcss libdvdread libdvdplay livdvdnav lsdvd xine-lib-extras-nonfree libdvdcss libdvdread libdvdplay flash-plugin libquicktime gstreamer-plugins-ugly gstreamer-plugins-bad`

Step 4: Install w32Codecs in order to play everything under the Sun.

> `<br />
wget www1.mplayerhq.hu/MPlayer/releases/codecs/mplayer-codecs-20061022-1.i386.rpm<br />
rpm -ivh mplayer-codecs-20061022-1.i386.rpm<br />
wget www1.mplayerhq.hu/MPlayer/releases/codecs/mplayer-codecs-extra-20061022-1.i386.rpm<br />
rpm -ivh mplayer-codecs-extra-20061022-1.i386.rpm`

(optional) Install VLC

> `yum install vlc<br />
yum install python-vlc mozilla-vlc`

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/06/10/multimedia-support-in-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-13" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/06/10/multimedia-support-in-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-13" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/06/10/multimedia-support-in-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-13" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/06/10/multimedia-support-in-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/06/10/multimedia-support-in-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.ehomeupgrade.com/2006/07/17/how-to-setup-debian-linux-desktop-with-full-multimedia-support-and-faster-processing/
 [2]: http://opensuse-community.org/codecs-kde.ymp
 [3]: http://opensuse-community.org/codecs-gnome.ymp
 [4]: http://download.videolan.org/pub/vlc/SuSE/10.3/vlc.ymp