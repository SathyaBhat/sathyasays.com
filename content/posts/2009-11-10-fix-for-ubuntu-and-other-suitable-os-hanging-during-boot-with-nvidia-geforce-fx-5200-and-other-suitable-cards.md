---
title: Fix for Ubuntu (and other suitable OS) hanging during boot with nVidia GeForce FX 5200 (and other suitable cards)
author: Bharath
type: post
date: 2009-11-09T18:33:43+00:00
url: /2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/
topsy_short_url:
  - http://u.sbhat.me/gk0a6D
categories:
  - News
tags:
  - 9.10
  - acpi
  - BIOS
  - boot
  - eye-candy
  - find
  - hassles
  - history
  - IM
  - install
  - Karmic
  - Karmic Koala
  - Koala
  - linux
  - LiveCD
  - MID
  - NVIDIA
  - open source
  - os
  - rm
  - tar
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - user
  - ux
  - X

---
This is one problem that has affected me the most in my history of Linux usage, so far. Imagine, for two full years I just din&#8217;t know that the solution to this problem is so simple. Too late of me to find out. Anyway, better late than never.

So the problem is, with my graphics card GeForce FX 5200, Ubuntu liveCD/post-installation boot will hang mid-way, with the boot-screen freezing or a big set of hexadecimal codes getting emitted. The cause is that ACPI settings, making some conflict (I suppose), with the Intel On-board Chipset. The &#8220;acpi=off&#8221; bppt option does NOT work in Ubuntu. Now, that&#8217;s what everyone suggests only to know it never helps. (Even Sathya suggested it to me)

It does not work because, BIOS settings dominate at the boot time. In other words, boot takes place by the settings in BIOS.So, the Ubuntu boot option &#8220;acpi=off&#8221; makes no sense. So, now does it become clear? You disable ACPI in BIOS!  Wow, that worked like magic for me. Now I am running Ubuntu 9.10 (Karmic Koala) on my PC without any boot problems.

However, shutdown does not work properly. Other things like restart and general things work fine.

So try that comment on whether it works.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-770" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-770" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-770" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>