---
title: Create a Fedora Bootable USB Pen/Flash Drive Easily using liveusb-creator
author: Sathya
type: post
date: 2008-10-16T18:56:33+00:00
url: /2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/
categories:
  - "Tips &amp; How-To's"
tags:
  - boot
  - bootable pendrive
  - creaing bootable pen drive
  - DE
  - distro
  - distros
  - download
  - Fedora
  - file
  - flash
  - flash drive
  - HAL
  - IM
  - install
  - iso
  - linux
  - LiveCD
  - liveusb
  - mount
  - net
  - New
  - open source
  - os
  - pen drive
  - Qt
  - rm
  - rpm
  - software
  - support
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - update
  - usb
  - USB drive
  - USB pen drive
  - user
  - ux
  - windows
  - X
  - yum

---
LiveCDs are a great way to try out (new) Linux distros on your system. [<img data-attachment-id="475" data-permalink="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/fedorausb/" data-orig-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/10/fedorausb.png?fit=184%2C84&ssl=1" data-orig-size="184,84" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="fedorausb" data-image-description="" data-medium-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/10/fedorausb.png?fit=184%2C84&ssl=1" data-large-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/10/fedorausb.png?fit=184%2C84&ssl=1" class="alignright size-medium wp-image-475" title="fedorausb" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/10/fedorausb.png?resize=184%2C84" alt="" width="184" height="84" data-recalc-dims="1" />][1]

Unfortunately CDs get scratched pretty easily, and can turn into a coaster pretty soon.

With prices of USB pen drives at rock bottom, they&#8217;re probably the best way to try out LiveCDs. Generally its not that easy to make a bootable LiveCD using USB pen/flash drives. If you&#8217;re a Fedora lover then here&#8217;s a very easy way to create a bootable USB pen drive.

<!--more-->liveusb-creator is software which allows you to create bootable USB drives from Fedora iso. Its got some really features like

  * Downloading of the latest Fedora release and previous ones
  * Automatic detection of external drives
  * Support for persistent layout &#8211; all your work done in the liveCD can be saved :D
  * Auto calculation of checksums to ensure download is correct
  * Works in Linux AND Windows!

<div>
  Its pretty simple to use, just select the ISO file, or choose to download off the net, select the target drive, choose the amount of space for persistent layout and click on the button to create LiveCD! As simple as that!
</div>

Download liveusb-creator:

  * [For Windows][2]
  * For Linux: 
      1. [Source Code][3]
      2. [RPM File][4]

Alternatively, you can install liveusb in Fedora by opening the terminal and typing `yum -y install liveusb-creator`.

Before installing, ensure that you run `yum -y install syslinux PyQt4 usermode` so that these packages are available.

liveusb-creator is authored by [Luke Macken][5] and [Kushal Das][6]

Thanks for the tip [Ashish][7].

**Update:** Narayanan <a href="http://www.techspikes.com/2008/10/install-linux-pendrive-usb/" target="_blank">mentions</a> UNetBootin which is a much better tool than liveusb-creator but doesn&#8217;t have the option to create a Persisten overlay like liveusb-creator does.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-474" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-474" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-474" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/10/fedorausb.png
 [2]: https://fedorahosted.org/releases/l/i/liveusb-creator/liveusb-creator-2.7.zip
 [3]: https://fedorahosted.org/releases/l/i/liveusb-creator/liveusb-creator-linux-2.7.tar.gz
 [4]: http://kushal.fedorapeople.org/packages/liveusb-creator-2.7-1.fc9.noarch.rpm
 [5]: http://fedoraproject.org/wiki/LukeMacken
 [6]: http://kushaldas.in/
 [7]: http://www.technospot.net/blogs/