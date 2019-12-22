---
title: '[How to] Setting up Frontech Tv Tuner in Linux'
author: Bharath
type: post
date: 2008-10-22T04:30:22+00:00
url: /2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - commands
  - driver
  - Fedora
  - internet
  - KDE TV
  - linux
  - LV
  - RIA
  - "tips-and-howto's"
  - tutorials
  - TV TIme
  
---
Continue I am personally a Frontech tv tuner user. I dont currently use it now but i was using in the past. I faced hell a lot of problems to get it working. It was sheer luck that i ran into the info [here][1] which saved me!!!! Thanks to Mann.

Here&#8217;s an excerpt from it

> 13/06/07- I cannot install my TV tuner card in fedora (this problem is irrelevant to my project, but i want it to be solved)
> 
> Causes:
  
> Its a cheap card and manufacture didn&#8217;t provide the sufficient information on its EEPROM. So fedora cannot recognize it automatically and hence driver is not loaded.

Solutions tried

  1. From internet and using the commands dmesg and lspci -v, i was able to figure out that it is <span style="#990000;">saa7130</span> chip based card.
  2. The thing to do here is to figure out the card type and tuner number by yourself and load the modules But in fedora there are 108 cards with different tuner number number. The last tuner number I tried was 71 and the list was more than 71 I think. So I sticked to card number 3 and tried different variations of tuner number from 1 to 71.

Continue Reading over at <a href="https://mann-linuxproject.blogspot.com/2007/06/problem3.html" target="_blank">Mann&#8217;s blog</a>

 [1]: https://mann-linuxproject.blogspot.com/2007/06/problem3.html