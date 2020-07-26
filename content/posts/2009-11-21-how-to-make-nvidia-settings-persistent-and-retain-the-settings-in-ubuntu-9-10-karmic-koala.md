---
title: '[How-to] Make nVidia settings persistent and retain the settings in Ubuntu 9.10 Karmic Koala'
author: Bharath
type: post
date: 2009-11-21T01:15:08+00:00
url: /2009/11/21/how-to-make-nvidia-settings-persistent-and-retain-the-settings-in-ubuntu-9-10-karmic-koala/
categories:
  - "Tips & How-To's"
tags:
  - 9.10
  - commands
  - distro
  - driver
  - drivers
  - file
  - forums
  - Home
  - Karmic
  - Karmic Koala
  - KDE
  - Koala
  - linux
  - NVIDIA
  - open source
  - Resolution
  - root
  - Screen Resolution
  - sudo
  - terminal
  - tips
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - xorg

---
Nvidia Proprietary Drivers need nvidia-settings to set screen resolution and change other settings. In previous versions of Ubuntu and in other distros to make them permanent (used in every session) you click the "Save to X configuration file". From Karmic on there is no xorg.conf by default!

As a result, nvidia-settings is not able to save the settings and every time I logged in I had  to change the resolution (Phew!!!). Then Sathya helped me. He gave me a [link from Ubuntu Forums][1]{#aptureLink_MZsWFB9Cv4}. Then I did the following to fix the problem:

<!--more-->

1. Press Crtl+Alt+F1 to go to tty1. (Crtl+Alt+F2 takes you to tty2 and so on. available till tty6).

2. You'll be taken to a terminal. Press Crtl+Alt+F7 to return to the GUI screen. Now you need to kill Xserver from there. Type &#8216;/etc/init.d/gdm stop' (use kdm in KDE).

3. If you are reading this and simultaneously following, you'll lose this screen in this step. Now, type

> sudo Xorg -configure

4. This gives an xorg.conf in your home directory. It would be named "xorg.conf.new".

5. Take this file to "/etc/X11" and rename it &#8216;xorg.conf'.

6. Now click "Save to X configuration file" in nvidia-settings. Note that you need root permissions to do this.

7. Now your settings will be saved. Make a copy of that file back in your home directory, if needed, and rename it to "xorg.conf.new" (replacing the original).

8. You're Done. Try logging off and back in.

 [1]: https://ubuntuforums.org/showthread.php?t=1260518
