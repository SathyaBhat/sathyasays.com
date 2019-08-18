---
title: Mounting .iso and .mds/mdf Files in Linux
author: Sathya
type: post
date: 2007-12-15T05:20:50+00:00
url: /2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/
categories:
  - News
tags:
  - '*buntu'
  - cat
  - commands
  - console
  - DE
  - distro
  - distros
  - DVD
  - file
  - IM
  - images
  - indic
  - iso
  - linux
  - mdf
  - mds
  - media
  - mount
  - mounting
  - nrg
  - open source
  - os
  - rm
  - root
  - show
  - software
  - sudo
  - switch
  - terminal
  - tutorials
  - Ubuntu
  - user
  - ux
  - windows
  - X

---
There are lots of times where you&#8217;d want to mount a CD/DVD image. Say your friend who uses his Windows box has given you a .iso file or a .mds/mdf file, created using Alcohol 120%. How would you mount them in Linux? Using the Terminal and making use of the [loop device][1],there is no need for any external software tools and utlities.

Here&#8217;s the steps:

  1. Open the Terminal/Console.
  2. Switch to root user(mounting more often than not requires root privileges, we&#8217;ll have a look as to how make media user-mountable later) by typing **<font color="#008000">su root</font>** *buntu users and others distros in which the root account is disabled, can skip this step.
  3. Type <font color="#008000">mount -o loop -t iso9660 /windows/movies/movies.mdf /movies/ </font> For users of distros where root account is disabled(like Ubuntu) prefix sudo to the above. So the command is <font color="#008000">sudo mount -o loop -t iso9660 /windows/movies/movies.mdf /movies/</font>

If the above command looks confusing,it&#8217;s pretty simple! Let&#8217;s dissect it.

mount command is pretty obvious, it&#8217;s the commnad used for mounting storage media and images of storage media.

-o loop(note that o is the letter o not the numeral zero, ie, 0) instructs the mount command to use the loopback device. -o stands for option, loop indicates loop back device. Intuitive, ain&#8217;t it?

-t iso9660 instructs the mount command that the image is of iso9660 format.

The next argument is the path to where the .mdf file is located.

The last argument is the path to which directory the media must be mounted.

The image below shows an example.

<p align="center">
  <a href="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/mount.jpg" title="mount.jpg"><img src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/mount.thumbnail.jpg?w=740" alt="mount.jpg" data-recalc-dims="1" /></a>
</p>

<p align="left">
  If all goes well, you shouldn&#8217;t be getting any messages, as in the image. For .iso files, the steps are the same, just replace the .mdf file by the .iso file. The above method should work for CloneCD&#8217;s .ccd and Nero&#8217;s .nrg files(I remember it worked long time ago, not so sure though, if anyone can confirm this it&#8217;d be great!)
</p>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-193" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-193" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-193" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://en.wikipedia.org/wiki/Loop_device