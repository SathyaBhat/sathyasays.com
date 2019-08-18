---
title: '[How-to] Solve Partitions not detected during Ubuntu 10.10 Maverick Meerkat Install'
author: Bharath
type: post
date: 2010-11-30T04:40:07+00:00
url: /2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/
topsy_short_url:
  - http://u.sbhat.me/gxqC9l
categories:
  - News
tags:
  - blog
  - boot
  - cat
  - DE
  - download
  - fdisk
  - find
  - forums
  - free
  - hard disk
  - IM
  - install
  - LiveCD
  - LV
  - os
  - partition
  - partitioning
  - Partitions
  - read
  - rm
  - software
  - terminal
  - Ubuntu
  - Ubuntu 10.10
  - user
  - windows
  - write
  - X
  - xp

---
It has been quite a while since I wrote here. Did not find time nor issues to write about.

I tried to install Ubuntu 10.10. The Partition Manager did not detect my partitions. It listed my entire hard disk as one &#8220;Unallocated Free Space&#8221;. I was puzzled. Everything was fine under Windows XP. Or so I thought.

My hard disk is a 60GB one., partitioned into 10, 25 and 25 GBs. My Disk Management under XP listed thus:

<!--more-->

<a rel="attachment wp-att-981" href="http://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/sathyasays/"><img data-attachment-id="981" data-permalink="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/sathyasays/" data-orig-file="https://sathyasays.com/wp-content/uploads/2010/11/sathyasays.bmp" data-orig-size="" data-comments-opened="1" data-image-meta="[]" data-image-title="diskmanagement-corrupted-partition-table" data-image-description="" data-medium-file="https://sathyasays.com/wp-content/uploads/2010/11/sathyasays.bmp" data-large-file="https://sathyasays.com/wp-content/uploads/2010/11/sathyasays.bmp" class="alignnone size-full wp-image-981" src="http://sathyasays.com/wp-content/uploads/2010/11/sathyasays.bmp" alt="" /></a>

Did you see that?? There was a 22.97 GB of Free Space which is not there at all! But otherwise I did not find any problem.

I even posted this problem in <a href="http://ubuntuforums.org/showthread.php?p=10145676" target="_blank">Ubuntu Forums</a>. And one of the users there
  
(by name Rod Smith) had given me a <a title="Diect Link" href="http://www.rodsbooks.com/missing-parts/index.html" target="_blank">link to his blog</a>, explaining a similar problem with the same symptom as mine and also a few solutions. You can actually take a look there to see how the hard disk gets listed as not partitioned.But, do not try those solutions unless you are pretty sure that, the problem mentioned in the blog, is exactly the same you are facing.

None of those helped though, so this is what I did.

I wanted a Windows software that can solve the problem in a click or two. I sceptically downloaded [Partition Magic 8.0][1].  Installed, and opened it. It was no later than I opened, when it said it has found overlapping partitions in hard disk. It also offered me to fix it. It was now when I had slight feeling of deja vu. My output from &#8220;fdisk -lu&#8221; command from Ubuntu LiveCD terminal said the same thing. I suggest even you do it as the first step to check the condition of your partition table.

I took Partition Magic&#8217;s offer. In a second, my partitions in Disk Management looked as they should. And when I booted back to Ubuntu Install, it was &#8211; &#8220;VOILA&#8221; it worked.

But again, there is also <a href="http://ubuntuforums.org/showthread.php?t=1510017" target="_blank">another Ubuntu Forums thread</a> that seems to work for a few others. It says something about deleting GPT data.

I hope one of the above solutions help. Also. Please comment any other solution that worked for you.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-980" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-980" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-980" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/11/30/how-to-solve-partitions-not-detected-during-ubuntu-10-10-maverick-meerkat-install/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.soft32.com/Download/free-trial/Partition_Magic/4-151-1.html "Link to Download Page"