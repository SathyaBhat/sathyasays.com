---
title: Xenserver and adding/attaching a new storage to a VM
author: Sathya
type: post
date: 2017-02-02T05:59:25+00:00
url: /2017/02/02/xenserver-and-addingattaching-a-new-storage-to-a-vm/
categories:
  - "Tips &amp; How-To's"
tags:
  - LVM
  - partitioning
  - virtualization
  - Xenserver

---
I had an instance today where a local VM(which is provisioned by Xenserver) was running low on disk space and wanted to increase the disk space allocated to it. Last time when I did it by increasing the space from within Xen Manager, I failed miserably(the VM was configured with LVM and neither pvscan or lvscan was able to see the increased space).

This time I tried a different approach:

  * rather than increasing the space of the attached disk, I created a new disk and attach it to the VM from Xenserver Management Console
  * Since the VM is configured with LVM, I decided to add the new disk as a Physical Volume(PV) and then extend the Logical Volume(LV) & Volume Group(VG)

Creating a new disk and attaching it to the VM from Xenserver management Console is fairly straightforward. First make note of the device to which the new disk is attached to. In this case, it is assumed to be xvdc. I'm also assuming that the volume group mesa-nl-vg exists and /dev/mapper/mesa&#8211;nl&#8211;vg&#8211;root is the logical volume path

Here's the steps ahead

`<br />
— Create new partition<br />
sudo fdisk /dev/xvdc<br />
— Create a new PV<br />
sudo pvcreate /dev/xvdc1</p>
<p>— Extend the VG<br />
sudo vgextend mesa-nl-vg /dev/xvdc1</p>
<p>— Extend LV. Note that the +100G indicates the size by which it should be increased<br />
sudo lvextend -L+100G /dev/mapper/mesa--nl--vg-root</p>
<p>— Resize the filesystem<br />
sudo resize2fs /dev/mapper/mesa--nl--vg-root<br />
` 

HowToGeek has a [nice writeup & cheatsheet on LVM][1], you should read that to get you up to speed with LVM.

 [1]: https://www.howtogeek.com/howto/40702/how-to-manage-and-use-lvm-logical-volume-management-in-ubuntu/
