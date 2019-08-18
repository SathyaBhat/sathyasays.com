---
title: Gain couple of Gigabytes of free space on Linux
author: Sathya
type: post
date: 2010-10-09T00:17:46+00:00
url: /2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/
topsy_short_url:
  - http://u.sbhat.me/bzTe0U
categories:
  - "Tips &amp; How-To's"
tags:
  - /dev
  - commands
  - DE
  - file
  - filesystem
  - free
  - Home
  - how-tos
  - IM
  - linux
  - New
  - os
  - partition
  - Partitions
  - root
  - sudo
  - "tips-and-howto's"
  - user
  - ux
  - X

---
> Block size of my partition is 4096 (it can be checked using dumpe2fs command). So reserved space on my partition is about 6,3 Gb and equal missing size from hd command.
> 
> How to change Reserved Block Count
> 
> Reserved Block Count for given partition can be changed using tune2fs command
> 
> <pre>sudo tune2fs -m 0 /dev/sda3</pre>
> 
> where /dev/sda3 is your file system identifier
> 
> -m option sets the percentage of reserved file system blocks (in this case it is being set to 0%)

via [How to gain couple of Gigabytes of free space on Linux?][1].

Important note from the post:

>  **You shouldn’t do this on partitions used by root (especially / and /root) and on partitions used by OS for logging and storing temporary files (e.g. /var and /tmp).**

I think this point should be mentioned at the top of the post, given how many new users don&#8217;t keep separate root (/) and separate home (/home) partitions.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-941" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-941" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-941" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://whileitcompiles.com/linux/how-to-gain-couple-of-gigabytes-of-free-space-on-linux/