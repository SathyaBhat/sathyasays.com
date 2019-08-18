---
title: 'How To: Access ext2/ext3 Formatted Linux Partitions in Windows'
author: Sathya
type: post
date: 2008-06-01T16:08:19+00:00
url: /2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/
categories:
  - "Tips &amp; How-To's"
tags:
  - applications
  - cat
  - DE
  - driver
  - ext2
  - ext3
  - FAT
  - FAT32
  - file
  - filesystem
  - install
  - linux
  - linux reader
  - mount
  - NTFS
  - os
  - partition
  - Partitions
  - personal
  - read
  - rm
  - software
  - softwares
  - support
  - tips
  - "tips-and-howto's"
  - tutorials
  - ux
  - windows
  - write
  - X

---
This is another one of those tips I always wanted to post, but kept forgetting :| So here goes.
  
Unlike Linux which can mount and access Windows&#8217; FAT, FAT16, FAT32 and NTFS filesystems, Windows is incapable of even acknowledging and detecting a Linux filesystem. Fear not, here are 3 softwares which can help in detecting your Linux partition under Windows

  * [Ext2fsd][1]&#8211; The most capable software of the lot. Has read/write support to your Linux partition. The 0.45 version supports replay of journal of a ext3 filesystem in case of a unclean shutdown of your Linux partition.
  * [Ext2 IFS][2] &#8211; Another very good software. Supports read/write, but doesnt replay the journal of a ext3 filesystem. It actually installs a pure _kernel mode_ file system driver, which means all applications can access your Linux partitions, and it appears in file dialogs of all applications.
  * [Linux Reader][3] &#8211; Like the name says, this is just a reader. Effectively you can&#8217;t write to it, neither is your partition available as a separate drive. You&#8217;ll have to open the application, then &#8220;extract&#8221; the file to your Windows. Personally I use this, since the lack of write access means that I can have a little peace of mind about my partition not getting corrupted due to writes(I&#8217;m not saying this WILL happen, but better be safe)

If you guys know of any other software then do drop a comment.

Cheers

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-311" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-311" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-311" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://ext2fsd.sourceforge.net/index.htm
 [2]: http://www.fs-driver.org/
 [3]: http://www.diskinternals.com/linux-reader