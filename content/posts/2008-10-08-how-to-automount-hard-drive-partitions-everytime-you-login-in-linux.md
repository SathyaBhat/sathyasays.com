---
title: '[How To] Automount Hard Drive Partitions Everytime You Login to Ubuntu Linux'
author: Bharath
type: post
date: 2008-10-08T06:32:30+00:00
url: /2008/10/08/how-to-automount-hard-drive-partitions-everytime-you-login-in-linux/
categories:
  - "Tips & How-To's"
tags:

  - linux
  - tutorials


---
Hello people,

This is Bharath Ram. I wanted to share with you an information I just found. This indeed solved my problem so I thought it would solve yours too.

In ubuntu (and may be in other distros) every time you login you never get your drives auto mounted (don't you?). This is a real pest especially when you would have set your wallpaper from an external drive or some other reason you want to use external drives for.

I have just found out a solution for this problem. That is no big deal but a small software called "pysdm". It was there for me in the ubuntu repositories but i seriously don't know about other distros. Install this software and if necessary open it after install (alt+f2 -> type "pysdm" -> enter) and in the options there say to automount your partition(s) at startup. Now the drives of ur hard disk will be mounted whenever you login. You won't have to manually/using computer mount them.

