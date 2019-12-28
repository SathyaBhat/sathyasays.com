---
title: '[How-to] Fix “E: Unable to parse package file /var/lib/apt/extended_states (1)”  error in Synaptic or apt-get'
author: Bharath
type: post
date: 2009-11-08T11:41:22+00:00
url: /2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/
categories:
  - "Tips &amp; How-To's"
tags:
  - apt-get
  - cloeses
  - DE
  - 'E: Unable to parse package file /var/lib/apt/extended_states (1)'
  - exe
  - exits
  - file
  - install
  - os
  - read
  - repo
  - rm
  - sudo
  - synaptic
  - terminal
  - unable
  - X

---
This is just a quick tip. If you are getting this error message in Synaptic:

> E: Unable to parse package file /var/lib/apt/extended_states (1)
  
> E: _cache->open() failed, please report

or this error in apt-get in command line:

> Reading package lists&#8230; Done
  
> Building dependency tree
  
> Reading state information&#8230; Error!
  
> E: Unable to parse package file /var/lib/apt/extended_states (1)

and both just fail to open or install, then just execute this in command line (terminal):

> sudo mv /var/lib/apt/extended\_states /var/lib/apt/extended\_states_tmp

You are done. Thanks to [this][1] post

 [1]: https://ubuntuforums.org/showthread.php?t=724916
