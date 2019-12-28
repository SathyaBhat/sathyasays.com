---
title: Installing And Configuring SMART in openSUSE10.3
author: Sathya
type: post
date: 2007-12-15T07:57:43+00:00
url: /2007/12/15/installing-and-configuring-smart-in-opensuse103/
categories:
  - "Tips &amp; How-To's"
tags:
  - applications
  - apt-get
  - cat
  - DE
  - Debian
  - download
  - file
  - guide
  - IM
  - install
  - linux
  - LV
  - open source
  - openSuSE
  - os
  - package manager
  - repo
  - repos
  - repositories
  - rm
  - rpm
  - Screen
  - show
  - smart
  - software
  - SUSE
  - synaptic
  - tar
  - terminal
  - tutorials
  - Ubuntu
  - update
  - ux
  - X
  - zypper

---
For the uninitiated, smart is the openSUSE equivalent of apt-get found in Debian based distributions such as Ubuntu.One of the biggest problems people who are used to apt-get face in openSUSE is that apt-get and Synaptic aren&#8217;t available in openSUSE and then they have no idea as to how to install software on their openSUSE machines. For them, and for many others, smart is the ideal solution. You can isntall software using the smart command prompt(&#8220;smart install <package-name>&#8221; or via the easy to use GUI. Like apt-get, smart also can resolve dependencies automatically. Here&#8217;s an easy guide to install smart on openSUSE 10.3.

<!--more-->

Open up the terminal and type the following

  * zypper sa -r https://download.opensuse.org/repositories/smart/openSUSE_10.3/smart.repo
  * zypper ref smart
  * zypper install smart
  * smart channel &#8211;add https://linux01.gwdg.de/~pbleser/files/smart/opensuse-10.3.txt
  * smart mirror &#8211;add https://linux01.gwdg.de/~pbleser/files/smart/mirrors-eu.txt
  * smart update
  * rpm &#8211;import <a href="https://linux01.gwdg.de/%7Epbleser/guru-rpm.asc" class="external free" title="https://linux01.gwdg.de/~pbleser/guru-rpm.asc" rel="nofollow">https://linux01.gwdg.de/~pbleser/guru-rpm.asc</a>
  * smart install smart-gui

7 easy steps to install smart. After this you can launch smart by clicking its entry in applications as shown

<p align="center">
  <a href="https://sathyasays.com/wp-content/uploads/2007/12/smart.jpg" title="smart.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/smart.thumbnail.jpg" alt="smart.jpg" /></a>
</p>

<p align="left">
  After launching Smart you&#8217;ll be greeted by this screen:
</p>

<p align="center">
  <a href="https://sathyasays.com/wp-content/uploads/2007/12/smart-screen.jpg" title="smart-screen.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/smart-screen.thumbnail.jpg" alt="smart-screen.jpg" /></a>
</p>

<p align="left">
  &nbsp;
</p>

<p align="left">
  After this, well, what? Start downloading those applications!
</p>
