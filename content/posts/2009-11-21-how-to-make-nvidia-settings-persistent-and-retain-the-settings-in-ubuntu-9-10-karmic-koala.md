---
title: '[How-to] Make nVidia settings persistent and retain the settings in Ubuntu 9.10 Karmic Koala'
author: Bharath
type: post
date: 2009-11-21T01:15:08+00:00
url: /2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/
categories:
  - "Tips &amp; How-To's"
tags:
  - 9.10
  - commands
  - DE
  - distro
  - distros
  - driver
  - drivers
  - file
  - forums
  - hassles
  - Home
  - IM
  - Karmic
  - Karmic Koala
  - KDE
  - Koala
  - linux
  - New
  - NVIDIA
  - open source
  - os
  - read
  - Resolution
  - rm
  - root
  - Screen
  - Screen Resolution
  - sudo
  - tar
  - terminal
  - tips
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - X
  - xorg

---
Nvidia Proprietary Drivers need nvidia-settings to set screen resolution and change other settings. In previous versions of Ubuntu and in other distros to make them permanent (used in every session) you click the &#8220;Save to X configuration file&#8221;. From Karmic on there is no xorg.conf by default!

As a result, nvidia-settings is not able to save the settings and every time I logged in I had  to change the resolution (Phew!!!). Then Sathya helped me. He gave me a [link from Ubuntu Forums][1]{#aptureLink_MZsWFB9Cv4}. Then I did the following to fix the problem:

<!--more-->

1. Press Crtl+Alt+F1 to go to tty1. (Crtl+Alt+F2 takes you to tty2 and so on. available till tty6).

2. You&#8217;ll be taken to a terminal. Press Crtl+Alt+F7 to return to the GUI screen. Now you need to kill Xserver from there. Type &#8216;/etc/init.d/gdm stop&#8217; (use kdm in KDE).

3. If you are reading this and simultaneously following, you&#8217;ll lose this screen in this step. Now, type

> sudo Xorg -configure

4. This gives an xorg.conf in your home directory. It would be named &#8220;xorg.conf.new&#8221;.

5. Take this file to &#8220;/etc/X11&#8221; and rename it &#8216;xorg.conf&#8217;.

6. Now click &#8220;Save to X configuration file&#8221; in nvidia-settings. Note that you need root permissions to do this.

7. Now your settings will be saved. Make a copy of that file back in your home directory, if needed, and rename it to &#8220;xorg.conf.new&#8221; (replacing the original).

8. You&#8217;re Done. Try logging off and back in.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-799" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-799" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-799" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://ubuntuforums.org/showthread.php?t=1260518