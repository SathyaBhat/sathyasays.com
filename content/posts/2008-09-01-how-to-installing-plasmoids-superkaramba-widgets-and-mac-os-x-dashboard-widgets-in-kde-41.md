---
title: '[How-To] Installing Plasmoids, SuperKaramba Widgets and Mac OS X Dashboard Widgets in KDE 4.1'
author: Sathya
type: post
date: 2008-09-01T15:32:01+00:00
url: /2008/09/01/how-to-installing-plasmoids-superkaramba-widgets-and-mac-os-x-dashboard-widgets-in-kde-41/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - browser
  - Dashboard
  - DE
  - Desktop
  - download
  - file
  - install
  - internet
  - KDE
  - kde 4.1
  - KDE4
  - KDE4.1
  - laptop
  - linux
  - login
  - Mac OS X
  - MacOSX
  - menu
  - net
  - New
  - open source
  - os
  - OS X
  - plasma
  - plasmoid
  - plasmoids
  - show
  - sudo
  - Super
  - SuperKaramba
  - support
  - tar
  - "tips-and-howto's"
  - tutorials
  - twitter
  - wallpaper
  - Widgets
  - X

---
Plasmoids are the little widgets that have made an appearance with KDE4. Plasmoids can basically do anything &#8211; from displaying your desktop and associated wallpaper to showing your laptop&#8217;s battery level,or even display the latest comics or post a tweet to twitter. While KDE 4 comes with some plasmoids, you can add extra plasmoids which do other things &#8211; from displaying your current system status to showing your current GPU temperature. Lets see how to do so.

<!--more-->

First bring up the Plasmoids list by clicking on the &#8220;cashew&#8221; at the top right corner and clicking on Add Widgets.

<p style="text-align: left;">
  Next, click on Install Widgets. This will show you 2 options &#8211; Install from Internet and Install from File<br /> <a href="http://www.flickr.com/photos/sathyabhat/2816927297/" target="_blank"><img class="aligncenter" src="http://farm4.static.flickr.com/3285/2816927297_eccecf82e8_m.jpg" alt="Plasmoids" /></a>
</p>

Now if you select Download from Internet, you&#8217;ll be brought up a window and you can choose a plasmoid from a list. Unfortunately not many are available in the list, so you&#8217;ll have to get the Plasmoids from other sources like [KDE-Look][1].

The good news is that in addition to native Plasmoids, SuperKaramba widgets and Mac OS X Dashboard widgets are also supported. Lets have a look at how to install them.

  1. Native Plasmoids 
      * tar -xvf plasmoid.tar.gz
      * cd plasmoid
      * mkdir build
      * cd build
      * cmake -DCMAKE\_INSTALL\_PREFIX=\`kde4-config &#8211;prefix\` ..
      * make
      * sudo make install OR su -c &#8220;make install&#8221;
Browser and Download the plasmoids from <a href="http://kde-look.org/?xcontentmode=70" target="_blank">KDE-Look</a>. Most likely the plasmoids are likely to be .tar.gz archives. Extract the archives using Ark or using tar. For extracting using tar, use the following command.

where plasmoid is the name of the file. Next compile the plasmoid.

  2. Superkaramba Widgets
SuperKaramba widgets are easier to install. Just download the Widget. The bring up the Plasmoid list as shown in the figure.
  
[<img class="aligncenter" src="http://farm4.static.flickr.com/3293/2816918895_ac1f2c6e65_m.jpg" alt="SuperKaramba" />][2]
  
above, Click on Install New Widgets -> Install from File and Choose Superkaramba. Next point to the Superkaramba(generally a .skz file). That&#8217;s it. the installed superkaramba just wont appear right now, but there&#8217;s a fix, so don&#8217;t worry.

  3. Mac OS X Dashboard Widgets
For Dashboard widgets, just download the widgets, and follow the same steps as above.

Now after installing the widgets may not appear in the menu. For this, logout and login, or open the Konsole, and type

> `kbuildsycoca4`

After a bunch of messages the newly installed Plasmoid will be available in the list

 [1]: http://kde-look.org
 [2]: http://www.flickr.com/photos/sathyabhat/2816918895/