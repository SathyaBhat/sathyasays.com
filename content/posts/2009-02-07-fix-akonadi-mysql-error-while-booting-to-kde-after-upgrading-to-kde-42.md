---
title: Fix Akonadi MySQL error while booting to KDE after upgrading to KDE 4.2
author: Sathya
type: post
date: 2009-02-07T01:18:17+00:00
url: /2009/02/07/fix-akonadi-mysql-error-while-booting-to-kde-after-upgrading-to-kde-42/
categories:
  - "Tips &amp; How-To's"
tags:
  - Akonadi
  - boot
  - commands
  - DE
  - IM
  - install
  - KDE
  - KDE 4.2
  - KDE4
  - linux
  - move
  - MySQL
  - open source
  - package manager
  - PIM
  - rm
  - root
  - Sabayon
  - switch
  - tar
  - terminal
  - tutorials
  - update
  - upgrading
  - X

---
I updated my KDE 4 installation to KDE 4.2 couple of days ago, and everytime I restart, KDE and Akonadi would throw me an error about MySQL server not being installed. Akonadi is the suite in KDE 4.2 &#8211; and I don&#8217;t use it &#8211; and sure as hell don&#8217;t want to install a MySQL database server just for this. So I decided to get rid of Akonadi &#8211; just fire up your package manager and uninstall it. It would probably remove the entire KDE PIM package &#8211; but meh, I&#8217;m good with that. 

Specifically in Sabayon, open the terminal, switch to root using 

> `su root`

and hit enter.

Next type 

> `equo remove akonadi`

That&#8217;s it.