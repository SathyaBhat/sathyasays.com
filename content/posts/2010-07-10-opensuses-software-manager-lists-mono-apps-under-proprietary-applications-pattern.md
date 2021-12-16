---
title: openSUSE’s software manager lists Mono apps under Proprietary Applications Pattern
author: Sathya
type: post
date: 2010-07-10T13:29:13+00:00
url: /2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/
topsy_short_url:
  - https://bit.ly/cW5jZA
categories:
  - General
tags:
  - 1-click install
  - applications
  - apps
  - bin
  - DJ
  - linux
  - Mono
  - openSuSE
  - software
  - SUSE
  - Unity

---
<img class="aligncenter size-medium wp-image-874" title="Mono Apps" src="https://i.sathyabh.at/ss/2010/07/mono-608x422.png" alt=""   srcset="https://i.sathyabh.at/ss/2010/07/mono-608x422.png 608w, https://i.sathyabh.at/ss/2010/07/mono-800x555.png 800w, https://i.sathyabh.at/ss/2010/07/mono.png 903w" sizes="(max-width: 608px) 100vw, 608px" />I've been using openSUSE for quite some time now, but this is definitely the first time that I've noticed this ( though probably because I tend to use zypper or the 1-click install rather than entering YaST).

Edit:
  
Output of `zypper lr -u`
  
<https://pastebin.com/awfeBeLP>

Output of `zypper se -s -i -t pattern`
  
<https://pastebin.com/DJc8HsLG>

Output of `zypper sl -d`
  
<https://pastebin.com/LxLREddG>

Edit 2: [Andreas Jaegar][1]{#aptureLink_6hGvH0hOns} comments on the above:

> Found it: The pattern is part of Mono Community pattern. As these ymp-patterns have no category, the software manager picks a pretty much random order. And it happens to be under proprietary software in this case.

 [1]: https://en.opensuse.org/User:A_jaeger
