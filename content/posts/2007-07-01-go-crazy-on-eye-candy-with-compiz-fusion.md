---
title: Go crazy on eye-candy with Compiz Fusion!
author: Sathya
type: post
date: 2007-07-01T17:52:39+00:00
url: /2007/07/01/go-crazy-on-eye-candy-with-compiz-fusion/
categories:
  - News
tags:
  - 3D
  - apps
  - apt-get
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - download
  - eye-candy
  - fun
  - fusion
  - gconf
  - git
  - GNOME
  - IM
  - install
  - KDE
  - kubuntu
  - move
  - New
  - os
  - plugin
  - repo
  - repos
  - repository
  - rm
  - sudo
  - switch
  - tar
  - terminal
  - Ubuntu
  - update
  - upgrade
  - ux
  - windows
  - X
  - xp

---
**DISCLAIMER: COMPIZ FUSION IS STILL UNDER DEVELOPMENT AND NOT STABLE. I DO NOT RECOMMEND INSTALLING IT, NEITHER AM I RESPONSIBLE FOR ANY DATA LOSS.**

With that away,
  
Compiz Fusion, is the new name to the project formed from the merger of compiz and Beryl.

[Here&#8217;s][1] a YouTube link(11.5MB) of Compiz Fusion Demonstration Video.

Here are the steps to install Compiz Fusion:

First **Remove Compiz and Desktop Effects**

> <font color="#008000">sudo apt-get remove compiz-core desktop-effects</font>

Add **Compiz-git repository**

Add the following to your /etc/apt/sources.list

> <font color="#008000">#Treviño&#8217;s Ubuntu feisty EyeCandy Repository (GPG key: 81836EBF &#8211; DD800CD9)<br /> <font color="#008000"># Many eyecandy 3D apps like Beryl, Compiz, Fusion and kiba-dock snapshots<br /> <font color="#008000"># built using latest available (working) sources from git/svn/cvs&#8230;</font><br /> <font color="#008000">deb http://download.tuxfamily.org/3v1deb feisty eyecandy</font><br /> <font color="#008000">deb-src http://download.tuxfamily.org/3v1deb feisty eyecandy</font> </font></font>

Add **Keys:**

> <font color="#008000"><font color="#008000"><font color="#008000">sudo wget http://download.tuxfamily.org/3v1deb/DD800CD9.gpg -O- | sudo apt-key add &#8211;</font> </font></font>

**Update your system**

> <font color="#008000"><font color="#008000"><font color="#008000">sudo apt-get update</font><br /> <font color="#008000">sudo apt-get upgrade</font> </font></font>

To **Install compiz fusion** in Ubuntu: (copy all and paste in a terminal)

> <font color="#008000"><font color="#008000"><font color="#008000">sudo apt-get install compiz compiz-gnome compizconfig-settings-manager compiz-fusion-plugins-extra libcompizconfig-backend-gconf</font> </font></font>

<font color="#000000">To <strong>Install compiz fusion </strong>in Kubuntu: (copy all and paste in a terminal)</font>

> <font color="#008000"><font color="#008000"><font color="#008000">sudo apt-get install compiz compiz-kde compizconfig-settings-manager compiz-fusion-plugins-extra libcompizconfig-backend-kconfig</font></font></font>

<font color="#000000">That completes installation!</font>

<font color="#000000">Start up Compiz Fusion , Press [Alt]+F2 and type</font>

> <font color="#008000"><font color="#008000"><font color="#008000">compiz &#8211;replace</font></font></font>

<font color="#000000">Let&#8217;s see how Compiz Fusion runs.</font>

<font color="#000000">First up, Compiz Fusion is not as fast(or smooth) as Beryl was, on the same system. I suspect that the merger of the codebase is reason why, in any case, even on my low end system(Pentium 4 at 2.4GHz, 256 MB RAM and a GeForce FX 5200), Compiz Fusion was not slow that it brought my system to a crawl, but not as swift as Beryl was.</font>

<font color="#000000">Most of the eye candy plugins are the same, save for some extra ones. Here&#8217;s few snapshots:</font>

<font color="#000000">First up, the Cube is now transparent by default, and yeah it looks awesome!</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-transparent-cube.jpg" title="Behold the transparent cube"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-transparent-cube.thumbnail.jpg" alt="Behold the transparent cube" /></a></font>
</p>

<font color="#000000">Another new effect is the &#8220;Cube Reflections&#8221;</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compizfusion-cubereflection.jpg" title="Cube reflections"><img src="http://sathyasays.wordpress.com/files/2007/07/compizfusion-cubereflection.thumbnail.jpg" alt="Cube reflections" /></a></font>
</p>

<font color="#000000">The Expose effect, now with reflections looks better than ever!</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-expose.jpg" title="Expose!"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-expose.thumbnail.jpg" alt="Expose!" /></a></font>
</p>

<font color="#000000">Scale plugin functions as ever, tiling up all open Windows neatly, and is one of the best reasons to have Compiz Fusion installed! Sample this desktop, all messed up, and you&#8217;ve to get to a particular app which is open:</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-hotspot-before.jpg" title="Before Hotspot"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-hotspot-before.thumbnail.jpg" alt="Before Hotspot" /></a></font>
</p>

<font color="#000000">Just move your mouse pointer to the upper right hand corner, watch!</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-hotspot-after.jpg" title="After Hotspot"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-hotspot-after.thumbnail.jpg" alt="After Hotspot" /></a></font>
</p>

<font color="#000000">The ring task-switcher, water effects and zoom plugins work as ever:</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-ring-task-switcher.jpg" title="compiz-fusion-ring-task-switcher.jpg"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-ring-task-switcher.thumbnail.jpg" alt="compiz-fusion-ring-task-switcher.jpg" /></a></font>
</p>

<font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-zoom1.jpg" title="After Zooming"> </a></font>

<p align="center">
  <font color="#000000"> Ring Task Switcher</font>
</p>

<p align="center">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-no-zoom.jpg" title="Before Zoom"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-no-zoom.thumbnail.jpg" alt="Before Zoom" /></a></font>
</p>

<p align="center">
  <font color="#000000">Before Zooming</font>
</p>

<p align="center">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-zoom1.jpg" title="After Zooming"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-zoom1.thumbnail.jpg" alt="After Zooming" /></a></font>
</p>

<p align="center">
  <font color="#000000">After Zooming</font>
</p>

<font color="#000000">Newer plugins include the Window blur plugin, which blurs the windows which are currently out of focus</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-blur-windows.jpg" title="Blur"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-blur-windows.thumbnail.jpg" alt="Blur" /></a></font>
</p>

<font color="#000000">And of course, if you wish to play with fire, there&#8217;s the Fire plugin</font>

<p style="text-align:center;">
  <font color="#000000"><a href="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-fire.jpg" title="Unleash your inner devil!"><img src="http://sathyasays.wordpress.com/files/2007/07/compiz-fusion-fire.thumbnail.jpg" alt="Unleash your inner devil!" /></a></font>
</p>

<font color="#000000">Also new are the Desktop Wall and Desktop plane plugins, which instead of placing the virtual desktop on different sides of cube, places them as a plane. There are also updated Animations(Rizr, Fade, Domino to name a few) for Window effects such as Minimize, Maximise etc.</font>

<font color="#000000">Have fun with Compiz Fusion!</font>

 [1]: http://youtube.com/watch?v=E4Fbk52Mk1w