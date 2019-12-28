---
title: An Easy Way to Transfer Data From A Linux Based Virtual Machine to Windows Host(And Vice Versa)
author: Sathya
type: post
date: 2008-05-18T06:32:48+00:00
url: /2008/05/18/an-easy-way-to-transfer-data-from-a-linux-based-virtual-machine-to-windows-hostand-vice-versa/
categories:
  - "Tips &amp; How-To's"
tags:
  - 2.22
  - accessible
  - cat
  - DE
  - distro
  - distros
  - Dolphin
  - download
  - driver
  - file
  - git
  - GNOME
  - how-tos
  - IM
  - install
  - internet
  - KDE
  - KDE4
  - Konqueror
  - linux
  - media
  - mount
  - Nautilus
  - net
  - New
  - os
  - read
  - rm
  - script
  - scripts
  - security
  - show
  - smb
  - software
  - softwares
  - Sun
  - tar
  - testing
  - tips
  - tutorials
  - user
  - ux
  - virtual machines
  - VirtualBox
  - virtualization
  - vm
  - VMWare
  - windows
  - X
  - xp

---
In my **<a href="https://sathyasays.com/wp-admin/sathyasays.com/2008/01/22/virtualization-concepts-and-basics-for-dummies" target="_blank">previous post</a>**, I&#8217;d mentioned about Virtualization &#8211; what it is, how useful it is to test new softwares, distros etc. Now while working in your virtual machine, you&#8217;d obviously save some data &#8211; do some wordprocessing, or compatibility testing of your programs, just to name some, all this would mean that the data would be stored in the virtual machine.

Now you would like to have this data on your physical machine. Or alternatively you may want to transfer data from your physical machine to your VM. Of course, you could always go about using the concept of shared folders, but this would require installation of guest-additions. On a linux-based guest, this would require running scripts, and these scripts most likely require kernel-header or kernel source files. Going by my past experience, in most default installations, the header files would not be installed, or simply be missing in all of Live-CD based distributions, requiring downloading of the packages from the Internet. Is there a simpler way of going about this? Yes! Lets see how. <!--more--> For this post, I&#8217;ve used Sun&#8217;s xVM VirtualBox 1.6, but the steps would be identical, albeit with different terminology, for other VM software like VMWare. The method requires that you share a Windows folder, most likely the folder to which you will transfer the data from the Virtual Machine. To share a folder, just right-click on it, click on Sharing & Security, put a Checkmark against &#8220;Share This Folder on the Network&#8221;, give a suitable name, and also put a Checkmark against &#8220;Allow Network users to change my files&#8221;. This is a critical part, else the shared folder would have read-only access.

<p style="text-align: center;">
  <a href="https://www.flickr.com/photos/sathyabhat/2500356930/" target="_blank"><img src="https://farm4.static.flickr.com/3203/2500356930_fb278c922a_m.jpg" alt="Sharing Properties"   /></a>
</p>

Next, Launch VirtualBox, click on the VM, then Click on Settings. In the list of different options, click on Network. At the Host Interfaces tab, click on the &#8220;+&#8221; icon.

<p style="text-align: center;">
  <a href="https://www.flickr.com/photos/sathyabhat/2500323906/" target="_blank"><img src="https://farm3.static.flickr.com/2420/2500323906_06c2a7b7ff_m.jpg" alt="Host Interface 1"   /></a>
</p>

<p style="text-align: left;">
  Give a suitable name, Click on OK. Next, Change the Attached to from NAT to Host Interface
</p>

<p style="text-align: center;">
  <a href="https://www.flickr.com/photos/sathyabhat/2500323908/" target="_blank"><img src="https://farm3.static.flickr.com/2210/2500323908_4af34764cf_m.jpg" alt="Host Interface 2"   /></a>
</p>

<p style="text-align: left;">
  You might be prompted by Windows regarding installation of new driver &#8211; about the driver not digitally signed, just click on Continue anyway and complete the driver installation. To verify that driver installation was successful, bring up the command prompt by Clicking on Start, Run, typing cmd. Open the prompt is up, type ipconfig to show a list of network interfaces. VirtualBox&#8217;s adapter will be shown as VirtualBox Host Interface 1(or whatever name you&#8217;d given earlier), with Media State as Media  disconnected.
</p>

<p style="text-align: center;">
  <a href="https://www.flickr.com/photos/sathyabhat/2500323920" target="_blank"><img src="https://farm3.static.flickr.com/2032/2500323920_578ff398b0_m.jpg" alt="IPConfig"   /></a>
</p>

<p style="text-align: left;">
  This is fine, don&#8217;t worry. Next start the VM. Once the VM is ready, the Host Interface would be  assigned an IP-address, this IP address is required for the VM to communicate with the Physical Machine. Make a note of the IP address, by following the same steps as above.
</p>

<p style="text-align: center;">
  <a href="https://www.flickr.com/photos/sathyabhat/2500323922/" target="_blank"><img src="https://farm3.static.flickr.com/2408/2500323922_e086bd6879_m.jpg" alt="IP Address, Assigned"   /></a>
</p>

<p style="text-align: left;">
  Now in the VM, mount a network drive with the IP adress noted as above. KDE & GNOME 2.22 users don&#8217;t have to mount the network drives, just open the File Manager(Konqueror in KDE 3series, Dolphin in KDE4, and Nautilus for GNOME users) and just type smb://<ip-address> in the address bar.
</p>

> <p style="text-align: center;">
>   <a href="https://www.flickr.com/photos/sathyabhat/2500356934/" target="_blank"><img src="https://farm3.static.flickr.com/2226/2500356934_5fc8b98572_m.jpg" alt="File Browser"   /></a>
> </p>

<p style="text-align: left;">
  <p style="text-align: left;">
    Now just copy the whatever files you want from the VM to this folder(or from the physical machine to the VM). The file will be available in the physical machine.
  </p>
  
  <p style="text-align: center;">
    <a href="https://www.flickr.com/photos/sathyabhat/2500356932/" target="_blank"><img src="https://farm3.static.flickr.com/2075/2500356932_2ab0a0c9bd_m.jpg" alt="File copied"   /></a>
  </p>
  
  <p style="text-align: left;">
    There you go! Your files are easily accessible! Simple as that!
  </p>
  
  <p style="text-align: left;">
    <p style="text-align: center;">
      <a href="https://www.flickr.com/photos/sathyabha</p"></a>
    </p>
