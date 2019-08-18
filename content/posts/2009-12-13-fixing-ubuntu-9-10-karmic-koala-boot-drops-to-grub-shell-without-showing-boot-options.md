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