---
title: '[How-to] Solve Partitions not detected during Ubuntu 10.10 Maverick Meerkat Install'
author: Bharath
type: post
date: 2010-11-30T04:40:07+00:00
url: /2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/
categories:
  - "Tips & How-To's"
tags:
  - partitioning
  - terminal
  - linux

---
It has been quite a while since I wrote here. Did not find time nor issues to write about.

I tried to install Ubuntu 10.10. The Partition Manager did not detect my partitions. It listed my entire hard disk as one "Unallocated Free Space". I was puzzled. Everything was fine under Windows XP. Or so I thought.

My hard disk is a 60GB one., partitioned into 10, 25 and 25 GBs. My Disk Management under XP listed thus:

<!--more-->

<a rel="attachment wp-att-981" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/sathyasays/"><img class="alignnone size-full wp-image-981" src="https://i.sathyabh.at/ss/2010/11/sathyasays.bmp" alt="" /></a>

Did you see that?? There was a 22.97 GB of Free Space which is not there at all! But otherwise I did not find any problem.

I even posted this problem in <a href="https://ubuntuforums.org/showthread.php?p=10145676" target="_blank">Ubuntu Forums</a>. And one of the users there
  
(by name Rod Smith) had given me a <a title="Diect Link" href="https://www.rodsbooks.com/missing-parts/index.html" target="_blank">link to his blog</a>, explaining a similar problem with the same symptom as mine and also a few solutions. You can actually take a look there to see how the hard disk gets listed as not partitioned.But, do not try those solutions unless you are pretty sure that, the problem mentioned in the blog, is exactly the same you are facing.

None of those helped though, so this is what I did.

I wanted a Windows software that can solve the problem in a click or two. I sceptically downloaded [Partition Magic 8.0][1].  Installed, and opened it. It was no later than I opened, when it said it has found overlapping partitions in hard disk. It also offered me to fix it. It was now when I had slight feeling of deja vu. My output from "fdisk -lu" command from Ubuntu LiveCD terminal said the same thing. I suggest even you do it as the first step to check the condition of your partition table.

I took Partition Magic's offer. In a second, my partitions in Disk Management looked as they should. And when I booted back to Ubuntu Install, it was - "VOILA" it worked.

But again, there is also <a href="https://ubuntuforums.org/showthread.php?t=1510017" target="_blank">another Ubuntu Forums thread</a> that seems to work for a few others. It says something about deleting GPT data.

I hope one of the above solutions help. Also. Please comment any other solution that worked for you.

 [1]: https://www.soft32.com/Download/free-trial/Partition_Magic/4-151-1.html "Link to Download Page"
