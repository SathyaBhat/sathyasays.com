---
title: '10 Rocking Features in 10 Days: Day 2: Bulletproof X and Graphical X configuration'
author: Sathya
type: post
date: 2007-10-11T02:57:29+00:00
url: /2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/
categories:
  - News
tags:
  - BulletProofX
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - dl
  - driver
  - file
  - fusion
  - gtk
  - IM
  - KDE
  - linux
  - net
  - New
  - os
  - read
  - Resolution
  - rm
  - show
  - software
  - subs
  - tar
  - Ubuntu
  - UNIX
  - user
  - ux
  - X
  - xp

---
<font size="2">Corey Burger continues in Part 2 of the 10 part series in <a href="http://fridge.ubuntu.com/node/1156">The Fridge</a>: </font><font size="2">Yesterday we kicked this whole thing off and took a look at Deskbar and Tracker. Today we turn our attention to X, the graphical subsystem of any Ubuntu (or Linux or Unix machine). As any existing Ubuntu user knows, not only do you need to configure X, but breakages can happen. Thankfully with Ubuntu 7.10, there comes a few new features to help out with these problems, including better auto detection and configuration, Bulletproof X and graphical X config, for those times when you really to play with something. But first, some explanations</font>

<font size="2"><strong>So what is X?</strong></font>

<font size="2">X, or X windowing system, is “a networking and display protocol which provides windowing on bitmap displays”, according to <a href="http://en.wikipedia.org/wiki/X_Window_System">Wikipedia</a>. It is also the basis of 99% of the GUIs on Linux and Unix systems such as Ubuntu.</font>

<font size="2"><strong>So what is this “autoconfiguration” stuff?</strong></font>

<font size="2">Thanks to the awesome work of all the X.org developers, Ubuntu 7.10 now is able to detect your video hardware and monitor better, meaning in most instances, everything should just work. But what about those times that it doesn’t?</font>

<font size="2"><strong>So I can config this graphically, right?</strong></font>

<font size="2">With 7.10, yes! The new displayconfig-gtk, written primarily by Sebastien Heinlein and based off the KDE systemconfig work, allows you to easily change the resolution, add another monitor, change your driver and more. Take a peak:</font>

<font size="2"><img src="https://wiki.ubuntu.com/GutsyGibbon/Beta?action=AttachFile&do=get&target=displayconfig1.jpg" alt="Graphical X configuration with displayconfig-gtk" /><br /> <strong>Saving your broken X.conf with BulletProofX</strong></font>

<font size="2">Of course, not everything can always be roses and champagne. Sometimes things break, including X. Like most software, X reads off a configuration file to determine how to start up, including what monitor(s) and video card(s) you have. If this file gets corrupted, things can break, very very badly:</font>

<font size="2"><a href="https://i0.wp.com/people.ubuntu.com/%7Ebryce/BulletProofX/100_0938.m.JPG" border="0"><img src="https://i0.wp.com/people.ubuntu.com/%7Ebryce/BulletProofX/100_0938.m.JPG?w=80%25" alt="X breaking, badly" data-recalc-dims="1" /></a></font>

<font size="2">But hey, all is not doom and gloom any more. With 7.10, you are no longer given a useless and arcane error dialog, you are now shown displayconfig-gtk to allow you to fix that broken config and get back on your feet:</font>

<font size="2"><a href="https://i0.wp.com/people.ubuntu.com/%7Ebryce/BulletProofX/100_1116.m.JPG" border="0"><img src="https://i0.wp.com/people.ubuntu.com/%7Ebryce/BulletProofX/100_1116.m.JPG?w=80%25" alt="displayconfig-gtk and BulletproofX saving the day" data-recalc-dims="1" /></a></font>

<font size="2">If you want to read a bit more, check out the X.org maintainer for Ubuntu, Bryce Harrington’s, <a href="http://people.ubuntu.com/%7Ebryce/BulletProofX/">article on BulletproofX</a></font>

<font size="2">Tomorrow, it’s off to explore all the new shiny with Desktop Effects, as brought to you by Compiz Fusion. Until then!</font>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-89" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-89" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-89" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/10/11/10-rocking-features-in-10-days-day-2-bulletproof-x-and-graphical-x-configuration/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>