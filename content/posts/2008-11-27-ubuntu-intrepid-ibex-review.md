---
title: Ubuntu Intrepid Ibex Review
author: Bharath
type: post
date: 2008-11-26T23:11:58+00:00
url: /2008/11/27/ubuntu-intrepid-ibex-review/
categories:
  - Reviews
tags:
  - Arch
  - boot
  - cat
  - compiz
  - crap
  - DE
  - download
  - driver
  - drivers
  - DVD
  - find
  - fusion
  - hardy
  - hassles
  - Human
  - Ibex
  - IM
  - install
  - internet
  - intrepid
  - Intrepid Ibex
  - LTS
  - Nautilus
  - net
  - New
  - NewHuman
  - NVIDIA
  - Nvidia Drivers
  - os
  - repo
  - repos
  - repositories
  - Resolution
  - review
  - Reviews
  - Screen
  - Screen Resolution
  - software
  - softwares
  - support
  - theme
  - Ubuntu
  - update
  - upgrade
  - X
  - xorg

---
I was very curious about Intrepid&#8217;s release. I just could not wait! I even pre-ordered the CD but downloaded the DVD without patience. I have not-so-fast a connection when it comes to downloading a DVD. In spite of it, I just downloaded. I even allocated HD and swap space for that and was just waiting to install it.

And what horrors!

<!--more-->

The first thing was that the live CD was hanging during boot(sort of Kernel Panic), the same way Gusty used to. Hardy was working completely well for me. I thought with every release Ubuntu will improve. But the first time I felt it is NOT so. I will have to boot from my on-board card if I want it to work.

Then, a small idea came upon. By which I upgraded to Intrepid through the update manager from Hardy. and after the update used the older kernel to boot. Intrepid did boot. I never knew that time that, this was not the end but just the beginning of problems.(What?!!!!)

The worst thing was nvidia driver will not install. A little searching over the internet revealed that it was not compliant with Hardy&#8217;s kernel.(What the hell??) It needs the kernel of Intrepid, which exactly does not work. And due to this even my screen resolution was not the one intended.

Even then i did not give up. I tried to install the older nvidia drivers that i used in Hardy (and Sathya was the one who suggested!! Thanks Sathya). I tried that, only to find out that it was not at all compliant with the new xserver-xorg-video. Downgrading to that of Hardy&#8217;s would crap up the whole thing.

This was the place that made me think. Why the hell should a person use Intrepid at all? Is it for the <a href="http://sathyasays.com/2008/10/31/how-to-install-newhuman-theme-from-intrepid-ibex-on-hardy-heron/" target="_blank">new theme, that can also so be applied in hardy?</a> . Is it because one would get latest versions of the softwares that could also be obtained in hardy [by adding repositories][1]?.  Is it for the new nautilus in Intrepid with tabs <a href="http://sathyasays.com/2008/11/11/how-to-upgrade-nautilus-in-hardy/" target="_blank">that could also be upgraded in hardy</a>? Is it the notion that owning the latest version means a great deal???  Or is it just that one wants to just make problems for his/her own self??

Whatever people would argue, I will never accept that Intrepid is stable. It is unstable, atleast when compared to its predecessor. Also, Hardy is LTS and so it has 3 years of support whereas Intrepid got only 1.5 years of support (from their respective dates of releases). Considering all of these facts, why should one upgrade/install intrepid at all???

Now I have changed to Hardy with all latest updates of softwares, the NewHuman(aka Dark Room) theme , new nautilus, nvidia restricted drivers and my ever-so-cool buddy compiz-fusion in action.

 [1]: http://sathyasays.com/2008/11/18/a-comprehensive-list-of-ubuntu-hardy-heron-and-ubuntu-intrepid-ibex-repositories/