---
title: '[How to] Tackling Screen Resolution Problems in Linux'
author: Bharath
type: post
date: 2008-10-26T04:30:46+00:00
url: /2008/10/26/how-to-tackle-screen-resolution-problems-in-linux/
categories:
  - "Tips & How-To's"
tags:

  - linux
  - tutorials


---
Many of us may feel screen resolution as the biggest pest in any OS. If we don't get the screen resolution we want we get real fed up with the UI (dont we?). Personally, I very much hate if screen resolution gets screwed up and also have faced a lot of problems on that.

So I thought I would make a post on the common problems I faced in ubuntu and I hope it would be useful for other distros too.

<!--more-->

**Sync. Out of Range**

This happened for me with Gusty install. Just press Ctrl +alt+f2 and you should get it all right.

**NVIDIA DRIVERS**

NVIDIA Proprietary Drivers when installed through repositories, can cause problems with the screen resolution. This really test the patience of an individual. So for people who don't know please install "nvidia-settings" first from the repositories(mostly, should be available there). There in the &#8216;Display Configuration' you should be having the screen resolution you need. Set it and if you want this resolution everytime you login then, click "Save to XConfiguration File" button. You SHOULD be root/ use &#8216;gksu' to do this.

Secondly, the problem could be that you may not be having the desired resolution in the drop-down menu. In that case, click on the "Advanced" button and add your desired but compatible resolution there. If it asks that it is unaviable and whether it should do what is possible say "Apply what is possible". I think that should the trick.

Thirdly, sometimes a bug is there where the set resolution may not become permanent even after saving it to the Xconfig file i.e. /etc/X11/xorg.conf . There is a way to fix this, however. Only by editing &#8216;edid.bin' using hex editor. Thats the best that could be done.

**PROCEDURE:**

Lets assume your screen resolution keeps changing to 979&#215;768 and you want 1024&#215;768 instead.

(i) Install ghex and read-edid.

(ii)Go to: “System -> Administration -> NVIDIA X Server Setting”

(iii) From the left hand list choose: “DFP-0 - (Nvidia Default Flat Panel)” (or whatever is your default panel)

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

(ix) Click decimal and enter &#8216;979', change to hexadecimal and see the value to be &#8216;3C9'

(x) You will have to split it as &#8216;C9' and &#8216;3'. And, in your hex editor it should be something like this

“`01 01 01 64 19` **C9** `77` **3**`1 00 26 30 4F 88 36 00 42 FF` ”

notice the positions of C9 and 3.

(xi) Again in your gnome caluculator input 1024 in dec mode and see in hex mode. The value should be &#8216;400'. Again split it as '00' and &#8216;4' and enter them in places of   &#8216;C9' and &#8216;3' respectively. `01 01 01 64 19` **00** `77` **4**`1 00 26 30 4F 88 36 00 42 FF` ”

(xii) If you want to change the Y resolution also i.e. &#8216;768' then follow the same procedure as that of above.

(xiii) Save your edid.bin under ghex and quit. Close scientific caluculator. Re-run parse-edid. You should be finding your desired resolution. `parse-edid: parse-edid version 1.4.1<br />
parse-edid: EDID checksum failed - data is corrupt. Continuing anyway.<br />
Mode "1024x768" # vfreq 57.645Hz, hfreq 46.462kHz`

(xiv) Make yourself root or using sudo/gksu copy edid.bin to /etc/X11.

(xv) Restart the computer and see if problem is solved. If not, Go on reading this.

(xvi) Open /etc/X11/xorg.conf as root, in gedit/vim.

(xvii) Then in the "Screen" section add the following: `Option "CustomEDID" "DFP-0:/etc/X11/edid.bin"`

replace the display device name (DFP-0) with your own that would be mentioned in nvidia-settings

(xviii) Save and restart PC and it should work

**LINUX KERNEL UPDATE**

After each kernel update, you will have to reinstall Nvidia's proprietary drivers. This should change with the DKMS (Dynamic Kernel Module Support) present in Linux Kernel 2.6.27 and Ubuntu Intrepid Ibex 8.10

**CONCLUSION**

The above three are the common problems I faced with Ubuntu.Feel free to mention problems you faced by posting a comment

A lot of thanks to this post by Fresh New Page Blog, for the post on editing EDID data
