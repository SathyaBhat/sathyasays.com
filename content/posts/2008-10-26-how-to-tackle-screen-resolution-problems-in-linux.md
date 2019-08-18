---
title: '[How to] Tackling Screen Resolution Problems in Linux'
author: Bharath
type: post
date: 2008-10-26T04:30:46+00:00
url: /2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - 8.10
  - bin
  - blog
  - DE
  - Desktop
  - distro
  - distros
  - dl
  - driver
  - drivers
  - dual
  - EDID
  - file
  - find
  - free
  - GNOME
  - Ibex
  - IM
  - install
  - intrepid
  - Intrepid Ibex
  - linux
  - login
  - LV
  - menu
  - New
  - NVIDIA
  - Nvidia Drivers
  - os
  - personal
  - read
  - repo
  - repos
  - repositories
  - Resolution
  - rm
  - root
  - Screen
  - Screen Resolution
  - sudo
  - support
  - sync
  - Sync. Out of Range
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - update
  - ux
  - X
  - xorg

---
Many of us may feel screen resolution as the biggest pest in any OS. If we don&#8217;t get the screen resolution we want we get real fed up with the UI (dont we?). Personally, I very much hate if screen resolution gets screwed up and also have faced a lot of problems on that.

So I thought I would make a post on the common problems I faced in ubuntu and I hope it would be useful for other distros too.

<!--more-->

**Sync. Out of Range**

This happened for me with Gusty install. Just press Ctrl +alt+f2 and you should get it all right.

**NVIDIA DRIVERS**

NVIDIA Proprietary Drivers when installed through repositories, can cause problems with the screen resolution. This really test the patience of an individual. So for people who don&#8217;t know please install &#8220;nvidia-settings&#8221; first from the repositories(mostly, should be available there). There in the &#8216;Display Configuration&#8217; you should be having the screen resolution you need. Set it and if you want this resolution everytime you login then, click &#8220;Save to XConfiguration File&#8221; button. You SHOULD be root/ use &#8216;gksu&#8217; to do this.

Secondly, the problem could be that you may not be having the desired resolution in the drop-down menu. In that case, click on the &#8220;Advanced&#8221; button and add your desired but compatible resolution there. If it asks that it is unaviable and whether it should do what is possible say &#8220;Apply what is possible&#8221;. I think that should the trick.

Thirdly, sometimes a bug is there where the set resolution may not become permanent even after saving it to the Xconfig file i.e. /etc/X11/xorg.conf . There is a way to fix this, however. Only by editing &#8216;edid.bin&#8217; using hex editor. Thats the best that could be done.

**PROCEDURE:**

Lets assume your screen resolution keeps changing to 979&#215;768 and you want 1024&#215;768 instead.

(i) Install ghex and read-edid.

(ii)Go to: “System -> Administration -> NVIDIA X Server Setting”

(iii) From the left hand list choose: “DFP-0 &#8211; (Nvidia Default Flat Panel)” (or whatever is your default panel)

(iv) Click the “Aquire EDID” button.

(v) Save “edid.bin” to the desktop. (click “Desktop” then click “OK”)

(vi) Close “NVIDIA X Server Settings” window.

(vii) In the terminal change directory to the Desktop

(viii) Type `parse-edid edid.bin | grep 'Mode'`

The output should look something like this:
  
`parse-edid: parse-edid version 1.4.1<br />
parse-edid: EDID checksum passed.<br />
Mode "969x768" # vfreq 60.004Hz, hfreq 48.363kHz`

Your edid data is set wrong here. Time to edit edid.bin

(viii) Open edid.bin in ghex and also open scientific caluculator ready at hand

(ix) Click decimal and enter &#8216;979&#8217;, change to hexadecimal and see the value to be &#8216;3C9&#8217;

(x) You will have to split it as &#8216;C9&#8217; and &#8216;3&#8217;. And, in your hex editor it should be something like this

“`01 01 01 64 19` **C9** `77` **3**`1 00 26 30 4F 88 36 00 42 FF` ”

notice the positions of C9 and 3.

(xi) Again in your gnome caluculator input 1024 in dec mode and see in hex mode. The value should be &#8216;400&#8217;. Again split it as &#8217;00&#8217; and &#8216;4&#8217; and enter them in places of   &#8216;C9&#8217; and &#8216;3&#8217; respectively. `01 01 01 64 19` **00** `77` **4**`1 00 26 30 4F 88 36 00 42 FF` ”

(xii) If you want to change the Y resolution also i.e. &#8216;768&#8217; then follow the same procedure as that of above.

(xiii) Save your edid.bin under ghex and quit. Close scientific caluculator. Re-run parse-edid. You should be finding your desired resolution. `parse-edid: parse-edid version 1.4.1<br />
parse-edid: EDID checksum failed - data is corrupt. Continuing anyway.<br />
Mode "1024x768" # vfreq 57.645Hz, hfreq 46.462kHz`

(xiv) Make yourself root or using sudo/gksu copy edid.bin to /etc/X11.

(xv) Restart the computer and see if problem is solved. If not, Go on reading this.

(xvi) Open /etc/X11/xorg.conf as root, in gedit/vim.

(xvii) Then in the &#8220;Screen&#8221; section add the following: `Option "CustomEDID" "DFP-0:/etc/X11/edid.bin"`

replace the display device name (DFP-0) with your own that would be mentioned in nvidia-settings

(xviii) Save and restart PC and it should work

**LINUX KERNEL UPDATE**

After each kernel update, you will have to reinstall Nvidia&#8217;s proprietary drivers. This should change with the DKMS (Dynamic Kernel Module Support) present in Linux Kernel 2.6.27 and Ubuntu Intrepid Ibex 8.10

**CONCLUSION**

The above three are the common problems I faced with Ubuntu.Feel free to mention problems you faced by posting a comment

A lot of thanks to this post by Fresh New Page Blog, for the post on editing EDID data

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-487" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-487" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-487" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>