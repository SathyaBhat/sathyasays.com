---
title: Fixing Ubuntu 9.10 Karmic Koala boot drops to grub shell without showing boot options
author: Bharath
type: post
date: 2009-12-13T05:17:03+00:00
url: /2009/12/13/fixing-ubuntu-9-10-karmic-koala-boot-drops-to-grub-shell-without-showing-boot-options/
categories:
  - "Tips & How-To's"
tags:
  - 9.10
  - AIR
  - console
  - cover
  - find
  - grub
  - Karmic
  - Karmic Koala
  - Koala
  - shell
  - show
  - Ubuntu
  - Wubi

---
I had this problem with a wubi install. Ubuntu would highly pester me and drop to command shell (that of grub) without showing the boot options (Why and who knows??). I every time will have to boot by manually entering boot options (really painful).  So I did this.

I entered the boot command of the "recovery console" manually by finding it out from grub.cfg through the Live CD. After getting to the repair option I selected the option "Update GRUB". Then the system did something I dont know. Then after returning to the options I selected the option similar to Boot Normally (whatever the exact wording was). Now, that was a miraculous finding. I restarted and boot worked like it should.

P.S-Something or the other helps me huh??
