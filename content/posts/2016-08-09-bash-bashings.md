---
title: Bash bashings..
author: Sathya
type: post
date: 2016-08-09T18:37:28+00:00
url: /2016/08/09/bash-bashings/
categories:
  - "Tips & How-To's"
tags:
  - bash
  - linux
  - popd
  - pushd

---
Since <a href="https://sathyabh.at/2016/07/12/in-with-the-new-job/" target="_blank">my new job</a> involves lot more of Linux, shell scripting bash and automation, I've been trying to brush up my Linux skills. Ran into this "problem" today where there's an init script which handles unicorn start/stop/reload and we were debugging some kinks around this. The init script had a chain of cd to the directory and the unicorn invoke script. Was trying to figure out why unicorn wasn't starting up, till I read a bit more and dropped to using echo to understand what's happening



This should give an idea. After experimenting with eval, pushd/popd, bash subroutines and some more things, both the Tech Architect and me did a facepalm when we realized&#8230; the script does a cd at start we really didn't need that chaining.

&nbsp;

(inb4  you-so-n00b etc etc)
