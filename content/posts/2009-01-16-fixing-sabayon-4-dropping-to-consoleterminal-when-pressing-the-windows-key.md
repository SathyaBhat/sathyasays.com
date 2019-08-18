---
title: Fixing Sabayon 4 dropping to console/terminal when pressing the Windows Key
author: Sathya
type: post
date: 2009-01-16T02:02:44+00:00
url: /2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/
categories:
  - "Tips &amp; How-To's"
tags:
  - bin
  - boot
  - console
  - DE
  - IM
  - keyboard
  - Meta
  - move
  - os
  - review
  - rm
  - root
  - Sabayon
  - Sabayon 4
  - Super
  - switch
  - switching
  - terminal
  - "tips-and-howto's"
  - update
  - windows
  - X

---
I&#8217;ve been trying out Sabayon 4 since the past weeks, and its been really great (will post a review soon). The one really irritating thing though, is on hitting the Windows(&#8220;Super&#8221;) key on the keyboard would result in Sabayon 4 switching VT&#8217;s. Now if you&#8217;ve no idea what VT&#8217;s are&#8230;. well that I would post some other time, basically you&#8217;d drop to a console prompt.

Anyways to remove this binding, open the Terminal, switch to root by typing `su root`

Now, type `rc-update del keymaps default; rc-update add keymaps boot` hit Enter, and reboot.