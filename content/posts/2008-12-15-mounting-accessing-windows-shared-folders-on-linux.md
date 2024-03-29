---
title: 'Mounting & Accessing Windows Shared Folders on Linux'
author: Sathyajith Bhat
type: post
date: 2008-12-15T03:31:27+00:00
url: /2008/12/15/mounting-accessing-windows-shared-folders-on-linux/
categories:
  - "Tips & How-To's"
tags:

  - linux

---
Well recently I'd bought an external 750GB USB hard disk, as I was running out of space on my laptop. Now this drive requires an external power source, so I just cant lug it everywhere with my laptop in my room so I thought I'll connect this to my other laptop, and share the drive (the other laptop is my office one, runs on Windows) and I could access this drive over WiFi. While accessing the drive contents via Dolphin was pretty easy thanks to the smb kparts (ie, to access just type smb://<ip-address>/<share-name> oh btw this works in Gnome 2.23 as well) trying to access the drive in Amarok via smb kparts would result in Amarok crashing. Hence I decided to mount it. I was sorta stuck, as I read the man pages for mount which mentioned smbfs is available but then mount kept throwing &#8216;unknown filesystem type smbfs".



Anyways after some Googling I mounted using CIFS, the command would be

> `mount.cifs //<host-or-ip-address>/<share-name> <path-to-mount><br />
` 

If the share requires authentication just add `-o user=<user-name>` to the above line. You will be prompted for password, just enter it, and the share will be mounted.

If you want a graphical tool, you can check out SMB4k<figure id="attachment_609" aria-describedby="caption-attachment-609" style="width: 300px" class="wp-caption alignnone">

<img class="size-medium wp-image-609" title="Smb4k" src="https://i.sathyabh.at/ss/2008/12/smb4k-300x187.png" alt="Smb4k"   srcset="https://i.sathyabh.at/ss/2008/12/smb4k-300x187.png 300w, https://i.sathyabh.at/ss/2008/12/smb4k-1024x640.png 1024w, https://i.sathyabh.at/ss/2008/12/smb4k.png 1280w" sizes="(max-width: 300px) 100vw, 300px" /><figcaption id="caption-attachment-609" class="wp-caption-text">Smb4k</figcaption></figure>
