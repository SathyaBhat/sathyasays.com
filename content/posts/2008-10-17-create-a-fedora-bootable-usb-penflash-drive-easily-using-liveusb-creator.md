---
title: Create a Fedora Bootable USB Pen/Flash Drive Easily using liveusb-creator
author: Sathyajith Bhat
type: post
date: 2008-10-16T18:56:33+00:00
url: /2008/10/17/create-a-fedora-bootable-usb-penflash-drive-easily-using-liveusb-creator/
categories:
  - "Tips & How-To's"
tags:
  - linux
  - terminal

---
LiveCDs are a great way to try out (new) Linux distros on your system. [<img class="alignright size-medium wp-image-475" title="fedorausb" src="https://i.sathyabh.at/ss/2008/10/fedorausb.png" alt=""   />][1]

Unfortunately CDs get scratched pretty easily, and can turn into a coaster pretty soon.

With prices of USB pen drives at rock bottom, they're probably the best way to try out LiveCDs. Generally its not that easy to make a bootable LiveCD using USB pen/flash drives. If you're a Fedora lover then here's a very easy way to create a bootable USB pen drive.

liveusb-creator is software which allows you to create bootable USB drives from Fedora iso. Its got some really features like

  * Downloading of the latest Fedora release and previous ones
  * Automatic detection of external drives
  * Support for persistent layout - all your work done in the liveCD can be saved :D
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

**Update:** Narayanan <a href="https://www.techspikes.com/2008/10/install-linux-pendrive-usb/" target="_blank">mentions</a> UNetBootin which is a much better tool than liveusb-creator but doesn't have the option to create a Persisten overlay like liveusb-creator does.

 [1]: https://i.sathyabh.at/ss/2008/10/fedorausb.png
 [2]: https://fedorahosted.org/releases/l/i/liveusb-creator/liveusb-creator-2.7.zip
 [3]: https://fedorahosted.org/releases/l/i/liveusb-creator/liveusb-creator-linux-2.7.tar.gz
 [4]: https://kushal.fedorapeople.org/packages/liveusb-creator-2.7-1.fc9.noarch.rpm
 [5]: https://fedoraproject.org/wiki/LukeMacken
 [6]: https://kushaldas.in/
 [7]: https://www.technospot.net/blogs/
