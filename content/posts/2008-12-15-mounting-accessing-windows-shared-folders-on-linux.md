---
title: 'Mounting & Accessing Windows Shared Folders on Linux'
author: Sathya
type: post
date: 2008-12-15T03:31:27+00:00
url: /2008/12/15/mounting-accessing-windows-shared-folders-on-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - 2.23
  - Amarok
  - cat
  - chm
  - DE
  - Dolphin
  - file
  - filesystem
  - GNOME
  - hard disk
  - KDE
  - laptop
  - linux
  - mount
  - mounting
  - os
  - read
  - Samba
  - smb
  - smb4k
  - "tips-and-howto's"
  - tutorials
  - usb
  - user
  - ux
  - WiFi
  - windows
  - X

---
Well recently I&#8217;d bought an external 750GB USB hard disk, as I was running out of space on my laptop. Now this drive requires an external power source, so I just cant lug it everywhere with my laptop in my room so I thought I&#8217;ll connect this to my other laptop, and share the drive (the other laptop is my office one, runs on Windows) and I could access this drive over WiFi. While accessing the drive contents via Dolphin was pretty easy thanks to the smb kparts (ie, to access just type smb://<ip-address>/<share-name> oh btw this works in Gnome 2.23 as well) trying to access the drive in Amarok via smb kparts would result in Amarok crashing. Hence I decided to mount it. I was sorta stuck, as I read the man pages for mount which mentioned smbfs is available but then mount kept throwing &#8216;unknown filesystem type smbfs&#8221;.

<!--more-->

Anyways after some Googling I mounted using CIFS, the command would be

> `mount.cifs //<host-or-ip-address>/<share-name> <path-to-mount><br />
` 

If the share requires authentication just add `-o user=<user-name>` to the above line. You will be prompted for password, just enter it, and the share will be mounted.

If you want a graphical tool, you can check out SMB4k<figure id="attachment_609" aria-describedby="caption-attachment-609" style="width: 300px" class="wp-caption alignnone">

<img data-attachment-id="609" data-permalink="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/smb4k/" data-orig-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?fit=1280%2C800&ssl=1" data-orig-size="1280,800" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="Smb4k" data-image-description="" data-medium-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?fit=300%2C187&ssl=1" data-large-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?fit=740%2C463&ssl=1" class="size-medium wp-image-609" title="Smb4k" src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k-300x187.png?resize=300%2C187" alt="Smb4k" width="300" height="187" srcset="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?resize=300%2C187&ssl=1 300w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?resize=1024%2C640&ssl=1 1024w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/12/smb4k.png?w=1280&ssl=1 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /><figcaption id="caption-attachment-609" class="wp-caption-text">Smb4k</figcaption></figure> 

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-608" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-608" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-608" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/12/15/mounting-accessing-windows-shared-folders-on-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>