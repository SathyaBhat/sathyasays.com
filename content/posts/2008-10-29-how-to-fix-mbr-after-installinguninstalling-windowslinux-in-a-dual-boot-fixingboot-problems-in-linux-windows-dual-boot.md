---
title: '[How To] Fix MBR after installing/uninstalling Windows/Linux in a dual boot'
author: Bharath
type: post
date: 2008-10-29T04:30:08+00:00
url: /2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/
categories:
  - "Tips &amp; How-To's"
tags:
  - AIR
  - boot
  - bootrec
  - commands
  - DE
  - dual
  - DVD
  - easybcd
  - find
  - fixboot
  - fixmbr
  - grub
  - guide
  - install
  - linux
  - LiveCD
  - Master
  - MBR
  - menu
  - move
  - Opera
  - os
  - partition
  - record
  - rm
  - root
  - show
  - software
  - sudo
  - terminal
  - "tips-and-howto's"
  - tutorials
  - ux
  - Vista
  - windows
  - X
  - xp

---
Many, who do a dual boot with any Linux and Windows will face the problem of Master Boot Record (MBR). In easier words, one of them (Windows or Linux) wont boot after installing/uninstalling the other. This is a small guide I hope many would find it useful.

**FIXING WINDOWS BOOT AFTER UNINSTALLING LINUX**
  
<!--more-->


  
**For Windows XP:** Boot the installation CD and select repair. Enter your windows installation drive number (shown there) and enter Administrative Password. Now run these two commands there one after the other  &#8212; &#8220;fixmbr&#8221; and &#8220;fixboot&#8221;. Optionally some people also run &#8220;bootcfg /rebuild&#8221;. You&#8217;re Done.

**For Windows Vista:** Boot from the installation CD/DVD and enter &#8220;Repair Windows&#8221; link at the left hand bottom of the dialog. Then go to command prompt . There run &#8220;bootrec /fixmbr&#8221; and &#8220;bootrec /fixboot&#8221; commands one after the other. That does it.

**FIXING GRUB AFTER INSTALLING WINDOWS**

1.Boot from a LiveCD and open the terminal..

2.There enter `sudo grub` to enter GRUB prompt.

3.Type `find /boot/grub/stage1` to find out your Linux partition.

4.Then use the device name that was output in the next command, say (hd0,1). Then the command would be `root (hd0,1)`.

5. After this, say `setup (hd0)`. Replace hd0 with your hard drive.

Now your GRUB should be installed fine. However, your windows&#8217; boot entry may not be in GRUB. You may choose to restore it while still being in your LiveCD or after booting into your hard-drive installed Linux.

To restore it:

1. Open /boot/grub/menu.lst of your Linux partition, in a text editor and get to the bottom where all the list of options to boot are found.

2. Add the following lines with your Windows name in the title and replace (hd0,0) with your own hard drive and partition:

> `title   Windows 95/98/NT/2000<br />
root   (hd0,0)<br />
makeactive<br />
chainloader+1`

3. Save and reboot.

**EDIT:**

**ADDING WINDOWS XP (AND OLDER) OPTIONS TO VISTA&#8217;S BOOT LOADER**

After installing Windows XP after Windows Vista and after restoring Vista&#8217;s bootloader one may find that xp or older windows&#8217; options will not be there. For this please make use of a software called [EasyBCD.][1] The installation and operation are self-explainatory. Just click on Add/Remove Entries and add your OS entry. You may also add your linux and mac entries to it. Also there is an option for having a common bootloader using NeoGrub.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-520" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-520" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-520" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://neosmart.net/dl.php?id=1