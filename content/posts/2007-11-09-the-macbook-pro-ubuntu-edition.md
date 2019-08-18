---
title: The MacBook Pro Ubuntu Edition
author: Sathya
type: post
date: 2007-11-09T15:12:36+00:00
url: /2007/11/09/the-macbook-pro-ubuntu-edition/
categories:
  - "Tips &amp; How-To's"
tags:
  - Apple
  - Arch
  - beta
  - boot
  - bootup
  - cat
  - DE
  - download
  - find
  - forums
  - Gutsy Gibbon
  - Home
  - IM
  - indic
  - install
  - Leopard
  - linux
  - Mac OS 10.5
  - Mac OS X
  - MacBook Pro
  - move
  - New
  - os
  - OS X
  - partition
  - partitioning
  - read
  - repo
  - rm
  - software
  - terminal
  - Ubuntu
  - ux
  - vm
  - write
  - X
  - xp

---
[TechieMoe][1] has put up an interesting [article][2] on his experience in getting Ubuntu Gutsy Gibbon up and running on his MacBook Pro. Here&#8217;s what he writes:

## Introduction:

Many times on LinuxForums I&#8217;ve come across folks who wanted to run Linux on an Apple computer. Most of the time the first question I ask of them is &#8220;If you have an Apple computer, why not just run OS X?&#8221; Until this past week, I could not have answered this question.

For several years I&#8217;ve run OS X on my Macbook Pro and been quite happy with it. The OS did what I wanted it to do and didn&#8217;t get in my way. I&#8217;ve been able to do work and play on it just fine. For those of you unaware, I write Java software for a living. I also sometimes coach a high school computer science competition. I spend a lot of time writing Java code and investigating new and exciting features in the language. One such feature is JavaDB. It&#8217;s completely new in Java 1.6, and can only be used with that version.

<!--more-->

I run 1.6 at work and I was having such a good time playing with JavaDB that I decided to send myself the code to work with at home. This is where I hit a wall. When I got home I realized OS X uses an Apple-modified version of Java 1.5, and in all my searching I couldn&#8217;t find any indication of when (or even if) Apple planned on releasing a new version of their JVM. Without 1.6, I couldn&#8217;t utilize JavaDB.

For the first time, Mac OS X was getting in my way. This was disappointing to say the least. Throughout my life when computers have told me I couldn&#8217;t do something I have tended to go to great lengths to prove them wrong. I decided to dedicate a couple of days to getting Linux installed on my Macbook Pro. Here is what happened.
  
<a title="install" name="install"></a>

## Initial Install

For this install, I used the latest available Ubuntu at the time (Ubuntu 7.10 &#8220;Gutsy Gibbon). Unless specified otherwise I followed all the instructions as given from the Ubuntu Macbook Pro Wiki (see [references][3]). The first thing on the wiki says to use BootCamp to resize your existing OS X partition. That no longer works, since the Boot Camp Beta has ended with the release of Mac OS 10.5 (Leopard) and Apple has pulled the download links. Even if you find a download (I did), the program blows up and says the beta has expired.

I ended up trying to resize the partition using **diskutil resizeVolume** in the Terminal. I ran the command given on the &#8220;Partitioning&#8221; section of the Wiki. It gave me an error. I looked it up and someone said to verify my HD with Apple&#8217;s Disk Utility. Lo and behold, I had errors. I rebooted into &#8220;Safe Mode&#8221; (hold Shift after the bootup sound) and the computer ran through all its diagnostics. That seemed to fix it since the next time I ran Disk Utility, it reported no errors.Then I rebooted and issued the **diskutil resizeVolume** command again. This time it got past the &#8220;Verifying&#8230;&#8221; stage and made it to the &#8220;Resizing Volume&#8221; stage. I was cautiously optimistic. At 88% resizing, I got an error &#8220;No space left on device (28).&#8221; I reduced the size of the partition I was trying to create and tried again. [Some research][4] on that error message suggested that my Parallels virtual harddrive was the culprit, since the resizing utility couldn&#8217;t move it. I uninstalled Parallels and tried again. This time it took, and I was instructed to reboot.

[Continue Reading][2] 

Wonder if Preshit would try this out!

 [1]: http://www.techiemoe.com/
 [2]: http://www.techiemoe.com/tech/macbookub.htm
 [3]: http://www.techiemoe.com/tech/macbookub.htm#refs
 [4]: http://installingcats.wordpress.com/