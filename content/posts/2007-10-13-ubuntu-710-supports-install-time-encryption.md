---
title: Ubuntu 7.10 Supports Install-Time Encryption
author: Sathya
type: post
date: 2007-10-13T07:50:00+00:00
url: /2007/10/13/ubuntu-710-supports-install-time-encryption/
categories:
  - News
tags:
  - 8.04
  - boot
  - DE
  - Debian
  - Desktop
  - dl
  - file
  - filesystem
  - fun
  - guide
  - Gutsy Gibbon
  - hard disk
  - hardy
  - Hardy Heron
  - Heron
  - Home
  - IM
  - install
  - laptop
  - linux
  - LiveCD
  - LTS
  - LV
  - LVM
  - New
  - os
  - partition
  - Partitions
  - read
  - rm
  - support
  - Ubiquity
  - Ubuntu
  - user
  - ux
  - vm
  - X

---
<p class="phxcms_normal_format" style="clear: both">
  &nbsp;
</p>

<p class="KonaBody">
  &nbsp;
</p>

<p align="left">
  If you have wanted to encrypt your Ubuntu installation on your hard drive quickly and easily, with Ubuntu 7.10 &#8220;Gutsy Gibbon&#8221; it&#8217;s become even easier now that the alternate installer supports encrypting partitions. However, the Ubuntu 7.10 &#8220;Gutsy Gibbon&#8221; Ubiquity installer currently lacks LVM and dm-crypt support.
</p>

<p align="left">
  The Ubuntu Wiki states: &#8220;Both the graphical and the alternate installer now support encrypting the hard disk.&#8221; However, using yesterday&#8217;s LiveCD with Ubiquity (v1.6.5) still hadn&#8217;t contained the encryption functionality when doing a manual partition. If the Ubiquity installer doesn&#8217;t support encrypting the hard drive in time for the Gutsy Gibbon release, we imagine it should ready in time for <a href="https://www.phoronix.com/scan.php?page=news_item&px=NjAxNA" target="_blank">Ubuntu 8.04 Hardy Heron</a>, which happens to be an LTS (Long Term Support) release.<!--more-->
</p>

<p align="center">
  <img src="https://www.phoronix.net/image.php?id=873&image=ubuntu_encrypt_1" title="Ubuntu 7.10 Supports Install-Time Encryption" />
</p>

<p align="left">
  The alternate installer encryption support was recently added and can be found in the Ubuntu 7.10 release candidate due out tomorrow or the final release of Gutsy Gibbon on October 18. The alternate installer (and the Ubiquity installer once supported) depends upon Debian&#8217;s partman and partman-crypto and then dm-crypt is used for handling the encrypted block devices. The rationale behind <a href="https://wiki.ubuntu.com/EncryptedFilesystemsInstaller" target="_blank">Ubuntu&#8217;s encrypted filesystem installer</a> is for supporting encryption whether you are using a notebook, desktop, or <a href="https://www.phoronix.com/scan.php?page=article&item=873&num=1#" id="KonaLink0" target="_top" class="kLink" style="text-decoration: underline ! important; position: static"><font style="color: #234865 ! important; font-family: verdana,arial,helvetica,sans-serif; font-weight: 400; font-size: 12px; position: static" color="#234865"><span class="kLink" style="color: #234865 ! important; font-family: verdana,arial,helvetica,sans-serif; font-weight: 400; font-size: 12px; position: static">server</span></font></a> and whatever information needs to be secured.
</p>

<p align="center">
  <img src="https://www.phoronix.net/image.php?id=873&image=ubuntu_encrypt_2" title="Ubuntu 7.10 Supports Install-Time Encryption" />
</p>

<p align="left">
  The Ubuntu installer supports encrypting all partitions on the hard drive (even SWAP) except for the boot partition. Alternatively, you could also leave everything unencrypted except for <em>/home/</em>. Another caveat to this encryption support is that the current implementation doesn&#8217;t support converting existing partitions to being encrypted. For taking the easy approach, during the alternate install process there is a &#8220;Guided &#8211; use entire disk and setup encrypted LVM&#8221; option.
</p>

<p align="left">
  This install-time dm-crypt-powered encryption for Ubuntu is great to see and is certainly needed for those storing sensitive information (especially on laptops). When the Ubiquity installer fully supports encrypted partitions it will be very nice and should be extremely easy to setup even for new <a href="https://www.phoronix.com/scan.php?page=article&item=873&num=1#" id="KonaLink1" target="_top" class="kLink" style="text-decoration: underline ! important; position: static"><font style="color: #234865 ! important; font-family: verdana,arial,helvetica,sans-serif; font-weight: 400; font-size: 12px; position: static" color="#234865"><span class="kLink" style="color: #234865 ! important; font-family: verdana,arial,helvetica,sans-serif; font-weight: 400; font-size: 12px; position: static">Linux </span><span class="kLink" style="color: #234865 ! important; font-family: verdana,arial,helvetica,sans-serif; font-weight: 400; font-size: 12px; position: static">users</span></font></a>. Ubuntu 7.10 &#8220;Gutsy Gibbon&#8221; is certainly shaping up to be an excellent Linux desktop release!
</p>

<p align="left">
  Author & Source:Michael Larabel, <a href="https://www.phoronix.com/scan.php?page=article&item=873&num=1">Phoronix</a>
</p>
