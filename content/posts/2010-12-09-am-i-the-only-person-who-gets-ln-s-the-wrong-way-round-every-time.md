---
title: Am I the only person who gets ln -s the wrong way round every time?
author: Sathyajith Bhat
type: post
date: 2010-12-08T22:25:06+00:00
url: /2010/12/09/am-i-the-only-person-who-gets-ln-s-the-wrong-way-round-every-time/

categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux

---
> `ln -s d1 d2 # Am I the only person who gets this the wrong way round every fucking time?`

Similar to most people who have posted there - I <span style="text-decoration: line-through;">used to</span> still get it wrong every time. It's become a habit for me to do a man ln or ln -help before I execute this command :\

Great tip here though:

> but then I finally found out about the relationship between ln and cp
  
> `cp existing new`
  
> `ln -s existing new`

via [ln -s d1 d2 # Am I the only person who gets this the wrong way round every fucking time? : programming][1].

 [1]: https://www.reddit.com/r/programming/comments/1qt0z/ln_s_d1_d2_am_i_the_only_person_who_gets_this_the
