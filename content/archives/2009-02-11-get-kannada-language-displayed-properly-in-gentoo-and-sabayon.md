---
title: Get Kannada Language displayed properly in Gentoo and Sabayon
author: Sathyajith Bhat
type: post
date: 2009-02-10T23:41:17+00:00
url: /2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/
categories:
  - News
tags:
  - indic
  - linux
  - terminal
  - tutorials

---
Well I was browsing through some Kannada sites the other day and all I got was big blocks.
  
Turned out that Gentoo and Sabayon didn't have support for displaying Kannada characters, though, I had no such problems with Hindi & Bengali characters [amongst others]. Changing the Character encoding in Firefox to Auto-detect or Unicode didn't work either. After doing a bit of searching, found the solution. So open the terminal, switch to root user and type

> `emerge -av lohit-fonts`

followed by 

> `fc-cache -f -v`

Restart your X server (ie, Logout, login) and you should be set!
