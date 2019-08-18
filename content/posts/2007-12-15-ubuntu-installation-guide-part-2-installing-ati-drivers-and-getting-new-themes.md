---
title: 'Ubuntu Installation Guide Part 2: Installing ATI drivers And Getting New Themes'
author: Aditya
type: post
date: 2007-12-15T05:03:43+00:00
url: /2007/12/15/ubuntu-installation-guide-part-2-installing-ati-drivers-and-getting-new-themes/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - cat
  - DE
  - download
  - dpkg
  - driver
  - drivers
  - eve-candy
  - file
  - GNOME
  - gtk
  - guide
  - IM
  - install
  - KDE
  - linux
  - login
  - Meta
  - New
  - open source
  - os
  - PIM
  - RIA
  - rm
  - root
  - Screen
  - sudo
  - synaptic
  - tar
  - terminal
  - theme
  - themes
  - tutorials
  - Ubuntu
  - user
  - ux
  - web
  - X
  - xorg

---
_Part 2 deals with installation of ATi drivers and visually enhancing that ubuntu_
  
**First of the Ati drivers**
  
Ati have released catalyst 7.11 for Linux. Download this from their [website][1]. Next login as root in ubuntu. Then double click the downloaded file. You will get different options here choose to run the file. The next screen asks you if you want install the drivers or if you want to generate a package. Choose to install the drivers. Then after the installation one will have to manually change the drivers to fglrx. To do this open up a terminal and type

> <font color="#008000"><code>sudo dpkg-reconfigure xserver-xorg</code></font>

Go through this wizard and at the part where you have to select the drivers(vesa will be the default one) press the up arrow button and go up to select the fglrx drivers.
  
Continue the wizard and restart X-server by pressing ctrl+alt+backspace.

 _Now let&#8217;s get some themes_
  
First GNOME& Xfce users go to <http://gnome-look.org> and KDE users to [kde-look.org.][2]

Now in gnome-look.org
  
Gutsy users can browse through metacity themes and download. Then under System->Preferences
  
select appearance and then select install theme.
  
Fiesty users need to download GTK 2.x themes.
  
For Gnomer&#8217;s
  
Go to synaptic and search for gcursor. Install it. Restart X. Go to gnome-look.org. Download your favourite cursor theme. Open gcursor and select install theme and voila instant pimpin.
  
That&#8217;s about it for now. More tutorials soon!

 [1]: http://ati.amd.com/support/drivers/linux/linux-radeon.html
 [2]: http://kde-look.org