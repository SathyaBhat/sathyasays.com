---
title: A Case of How NOT to Remaster A Distro
author: Sathya
type: post
date: 2008-01-13T16:57:15+00:00
url: /2008/01/13/a-case-of-how-not-to-remaster-a-distro/
categories:
  - General
tags:
  - applications
  - cat
  - community
  - DE
  - distro
  - forums
  - free
  - games
  - GPL
  - IM
  - irc
  - license
  - linux
  - LV
  - Master
  - move
  - New
  - open source
  - os
  - read
  - remastering
  - RIA
  - rm
  - script
  - software
  - subs
  - support
  - Ubuntu
  - Ultumix
  - Unity
  - user
  - ux
  - warning
  - web
  - windows
  - WINE
  - X

---
While browsing through [TuxMachine&#8217;s][1] articles, I read this article. Budding people interested in creating a Distro, make sure you read this.

One of the core principles of open source development is “freedom”. As such, there are few limitations for developers and end users to take the work of others and move it into a direction they deem better. This has led to a proliferation of Linux distributions, remasters and scores of applications that sometimes are hard to distinguish from other
  
distributions, remasters or applications. It’s not an ideal situation but somehow quality material always seems to stick around, while the rest sinks back into oblivion.

Another core principle is perhaps “respect”. Freedom is never an absolute. You can fork a distribution or an application, but you don’t have the freedom to remove or change the underlying licenses. You respect that. Why this introduction?

<span style="font-weight: bold">The case of Ultumix</span>

<!--more-->


  
In preparation for the series about PCLinuxOS I ran into [Ultumix,][2] a remaster of PCLinuxOS. I have nothing against remasters. In fact, I created a customized version of Ubuntu for the book about Linux. Hence, I know it is not easy to do, though far easier than to create a new distribution of your own. I wouldn’t dream of rebranding it with another name. It’s Ubuntu and it stays Ubuntu. However, bread crumbs of Ultumix do give an insight into why it’s website says the following:

> WARNING! PCLinuxOS Forums and IRC Chat
  
> The PCLinuxOS community has informed me that they do not want users of
  
> Ultumix getting support from their forum or IRC chat. If you want
  
> assistance please use the links at the top of this page. Thanks.

What caused this stern stand by the PCLinuxOS community? Well, the first iteration of the Ultumix remaster had Cedega in it. [Cedega][3] is a commercial implementation of Wine that enables Linux users to play a selection of Windows-based games. It’s subscription-based and it is definitely not allowed to distribute it with your distribution unless You have persmission to do so (and -most likely- paid Transgaming for it). For this reason Ultumix was banned from Linux Tracker in November 2007.

<span style="font-weight: bold">Learning from your mistakes?</span>
  
Now, everyone is entitled to make a mistake. What would you do after a foul up like this? Yes, you would read up on free and open source licensing and make sure that the next iteration would at least be free of problems. Apparently, the producer of Ultumix forgot to do that, because early December 2007 he released a new version of Ultumix
  
without Cedega, but with a nice logo **that stated that this distribution was released under the GPL v3**. “Say again?”. Yes, he decided that the kernel, the tools, the applications everything should be released under the GPL v3. Fortunately a few people got in touch with him, so he could post in [the Linux Questions forum][4]:

> Some have pointed out that I will make people angry if I
  
> release this under the GPLv3 so as of this moment on 12/03/07 at 04:23
  
> PM Pacific Standard Time any software that is released under the GPLv2
  
> will stay under the GPLv2. Also any software I created or released
  
> myself will be under the GPLv3. I just needed to get that out of the
  
> way.

People getting angry? You mean: getting sued for blatant violations of underlying licenses. Ignorance is not bliss. Too bad that this tainted version was released via The Pirate Bay where it will be available for quite a long time.

Continue Reading at [OpenSourceLearning][5]

> 
>

 [1]: http://tuxmachines.org/
 [2]: http://www.mindblowingidea.com/Ultumix
 [3]: http://www.transgaming.com/
 [4]: http://www.linuxquestions.org/reviews/showproduct.php?product=806
 [5]: http://opensourcelearning.info/blog/?p=720