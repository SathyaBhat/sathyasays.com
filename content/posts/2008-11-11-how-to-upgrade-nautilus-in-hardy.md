---
title: '[How to] Upgrade nautilus in hardy'
author: Bharath
type: post
date: 2008-11-10T18:36:48+00:00
url: /2008/11/11/how-to-upgrade-nautilus-in-hardy/
categories:
  - "Tips &amp; How-To's"
tags:
  - 2.22
  - 2.23
  - Arch
  - Firefox
  - GNOME
  - hardy
  - Hardy Heron
  - Heron
  - intrepid
  - login
  - Nautilus
  - Pidgin
  - repository
  - theme
  - "tips-and-howto's"
  - tutorials
  - Ubuntu

---
This is my small post on how to upgrade nautilus in hardy to that version in Intrepid. As of know, the upgrade option in hardy repositories isn&#8217;t there yet. And, its true that the 2.23 version of Nautilus has tab facility like in Firefox. However, Ubuntu Hardy Heron which has Gnome 2.22 version and so doesn&#8217;t have that option.

For this reason I wanted to upgrade nautilus and kept searching for the whole day. Without hope i searched for one last time and found out exactly what i needed. The only way I know to upgrade nautilus is adding the intrepid repository in hardy.

Here&#8217;s how you can go about doing so

1. Add this repository in hardy :-

deb <http://archive.ubuntu.com/ubuntu>{.http} intrepid main restricted universe multiverse

2. Update your repository sources list 

3. Upgrade nautilus 

4. Logout and login.

There also many other packages in this repository since this is the original ubuntu repository. Optionally, you may also like to download them. Some of them include firefox,usplash theme,pidgin,gnome panel etc.