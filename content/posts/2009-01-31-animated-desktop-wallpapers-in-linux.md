---
title: 'Animated Desktop Wallpapers in Linux: Presenting XWinWrap'
author: Bharath
type: post
date: 2009-01-30T22:26:32+00:00
url: /2009/01/31/animated-desktop-wallpapers-in-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - animated wallpapers
  - Arch
  - Command-line
  - compiz
  - DE
  - Desktop
  - download
  - Dreamscene
  - eye-candy
  - file
  - GNOME
  - icons
  - IM
  - install
  - KDE
  - linux
  - login
  - Mplayer
  - New
  - openSuSE
  - os
  - rm
  - root
  - Screen
  - software
  - SUSE
  - tar
  - user
  - ux
  - Vista
  - wallpaper
  - wallpapers
  - web
  - windows
  - write
  - X
  - XWinWrap
  - YaST
  - zypper

---
I am probably writing this post too late. To many out there this could be an old news. But, since it was long since I wrote on Sathya Says, (been searching for something to write about) and also this post is worth featuring here, I decided to write this. ;)

Recent times has given birth to many ideas in beautifying one&#8217;s desktop. Windows+Linux and related people contribute much towards this. Like [Stardock][1], for example, is a company that offers variety of products to customise your Windows desktop. [WinCustomize.com][2] is also another website worth mentioning.

<!--more-->On the other hand, websites like 

[Gnome-Look.org][3] , [KDE-Look.org][4] or [XFCE-Look.org][5] provide excellent customisation for linux desktops.

Of many ways to customise desktop Animated Wallapers (think Dreamscenes in Vista) are one cooool way to beautify the desktop. Many out there may know about and/or how to do this on Windows desktops. However, I want to throw light on doing this in a linux desktop.

Now all you need to do is download a software called [XWinWrap][6]. The link for deb file is [here][7]. You can compile from source, by downloading the source from [here][8]. openSUSE users can install via zypper or YaST, more info [here][9]. After installing run with &#8220;xwinwrap&#8221; command. For a list of command-line parameters for the command go [here][6].

To use the GLMatrix screensaver use:

> `xwinwrap -ov -fs -- /usr/lib/xscreensaver/glmatrix -root -window-id WID`

<img class="alignnone" src="http://tombuntu.com/wp-content/uploads/2008/12/xwinwrap1.jpg" alt=""   />

To use a video as wallpaper using MPlayer:

> `xwinwrap -ov -fs -- mplayer -wid WID -quiet -loop 0 video.ogg`

Whenever you want to return to your normal desktop just kill XWinWrap:

> `killall xwinwrap`

The animated wallpaper appears at the top of the desktop though. So the desktop icons may not be visible. So you will have to access your programs from links at other places (like I arranged them in my top panel). And also this makes the system slow, especially with compiz on, unless you got a moderately fast PC. Plus, if you like you can also add this to the start-up programs so that it is on every time you login.

And here&#8217;s my own Desktop :P

[<img class="alignnone" src="http://img300.imageshack.us/img300/5684/screenshotrz2.png" alt=""   />][10]

I like this idea and I hope you will too. ENJOY!!!!

* * *Thanks to Tom for 

[this post][11] and pic.</p>

 [1]: http://stardock.com/
 [2]: http://wincustomize.com
 [3]: http://gnome-look.org
 [4]: http://kde-look.org
 [5]: http://xfce-look.org
 [6]: http://swik.net/xwinwrap
 [7]: http://tech.shantanugoel.com/resources/downloads/shantz-xwinwrap.zip
 [8]: http://webcvs.freedesktop.org/xapps/xwinwrap/
 [9]: http://en.opensuse.org/Xwinwrap
 [10]: http://img300.imageshack.us/img300/5684/screenshotrz2.png
 [11]: http://tombuntu.com/index.php/2008/12/15/animated-wallpaper-on-your-ubuntu-810-desktop/
