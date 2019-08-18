---
title: openSUSE 11.2 Milestone 8 And Release Candidates(RC) add boot from USB flash disk option, here’s how to use it
author: Sathya
type: post
date: 2009-10-22T19:24:28+00:00
url: /2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/
categories:
  - "Tips &amp; How-To's"
tags:
  - /dev
  - blog
  - boot
  - commands
  - DE
  - DVD
  - file
  - flash
  - flash drive
  - IM
  - install
  - iso
  - KDE
  - KDE4
  - linux
  - LiveCD
  - media
  - openSuSE
  - openSUSE 11
  - os
  - personal
  - rm
  - root
  - support
  - SUSE
  - switch
  - terminal
  - "tips-and-howto's"
  - tutorials
  - usb
  - user
  - ux
  - X

---
Howdy folks! Been a \*loong\* time since I last posted isn&#8217;t it? Just been busy with work & travel (won&#8217;t bore you with the details, just check [my personal blog][1]{#aptureLink_20DGMzo67U}).
  
I&#8217;ve been looking forward to the upcoming openSUSE 11.2 version ( it&#8217;s no secret that I&#8217;m a fan of [openSUSE][2]{#aptureLink_yxkV6H9kot}), but the main problem for me was that I don&#8217;t like holding onto optical media, and have a 8gig USB flash disk, especially for these things.

Unfortunately  openSUSE has been lacking a install/boot from USB flash drive for quite sometime, upto now that is. The last Milestone (M8) and the first release candidate, RC1 includes support for booting from USB flash disks.

You will need access to a Linux environment, inorder to accomplish this step.

<!--more-->Once you&#8217;re in Linux, open the terminal. Insert your USB flash disk. ait for few moments  for the flash disk to be detected. Then, switch to root user by typing


  
`su root`

And then type in
  
`dd if=image.iso of=/dev/sdX bs=4M`
  
Replacing image.iso with the full path of the iso file
  
& sdX with your actual device name of your flash drive. Be careful while entering the device name, all data will be wiped out, ensure you&#8217;ve entered the right one!

And, that&#8217;s about it. Reboot, using the USB flash disk as boot device & voila!

Note: I&#8217;ve tried this with the KDE4 LiveCD version, if anyone else has tried the DVD version please drop a comment!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-758" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-758" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-758" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyabh.at/
 [2]: http://en.opensuse.org/