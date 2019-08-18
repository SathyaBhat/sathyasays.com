---
title: Fixing Ubuntu 9.10 Karmic Koala boot drops to grub shell without showing boot options
author: Bharath
type: post
date: 2009-12-13T05:17:03+00:00
url: /2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/
categories:
  - "Tips &amp; How-To's"
tags:
  - 9.10
  - AIR
  - boot
  - console
  - cover
  - find
  - grub
  - IM
  - install
  - Karmic
  - Karmic Koala
  - Koala
  - rm
  - shell
  - show
  - tar
  - Ubuntu
  - update
  - Wubi
  - X

---
I had this problem with a wubi install. Ubuntu would highly pester me and drop to command shell (that of grub) without showing the boot options (Why and who knows??). I every time will have to boot by manually entering boot options (really painful).  So I did this.

I entered the boot command of the &#8220;recovery console&#8221; manually by finding it out from grub.cfg through the Live CD. After getting to the repair option I selected the option &#8220;Update GRUB&#8221;. Then the system did something I dont know. Then after returning to the options I selected the option similar to Boot Normally (whatever the exact wording was). Now, that was a miraculous finding. I restarted and boot worked like it should.

P.S-Something or the other helps me huh??

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-810" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-810" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-810" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>