---
title: "Reviving my dead Windows 8 install with no bootable USB/DVD and Linux Mint & Cr48"
author: Sathyajith Bhat
type: post
date: 2013-02-25T16:52:13+00:00
url: /2013/02/25/reviving-my-dead-windows-8-install-with-no-bootable-usbdvd-and-linux-mint-cr48/
categories:
  - News
  - "Tips & How-To's"
tags:
  - cr48
  - linux
  - mint
  - windows
---

Couple of months ago, just about a month before #cpgweds - the engagement my Envy 14 laptop started showing signs of dying - weird noises coming from the vents, system freezing arbitrarily, system getting incredibly hot - and that's really unusual because the Envy's cooling system is probably one of the best that I've seen in a laptop. Soon enough, it became clear that a fan was not working - my idle temperatures hit 85 degrees C, and start any game or even xbmc, and the temperatures would hit 95-100 and shutdown sooner or later.

And soon enough, HP's diagnostics started informing me that my system fan's dead during bootup. To figure out which one's the dead one, I dismantled the Envy(I was out of warranty anyway) and switched on the laptop - and was kinda surprised that the laptop was still able to run at all.

So now, while I experimenting with switching off/on to see if I can "jump" start the fan, I ended up screwing up my Windows 8 install - and ended up with a BSOD( bad_system_config_info) boot loop. No amount of reboots could help and I was stuck there. Also, thanks to the new "enhancements" F8-mashing would not result in the start up menu being shown up.

I had to resort to switching off in middle of a boot process to bring up the start up menu so that I could try our Windows 8's Reset/Refresh. Unfortunately, both Reset and Refresh failed for some reason. I tried to refresh but somehow my custom recovery image got wiped out.. with no backup of it. Reset failed to work as well and I was back to status quo - BSOD Boot Loop.

Generally I keep a bootable Live USB with me, but this time I didn't have that either, neither did I have any bootable DVDs. So my situation now:

- Windows is stuck on a BSOD boot loop
- No bootable USB or DVDs present
- No other laptops/desktops available except......
- .... Except for the Cr48.

Yep, the Cr48 turned to be my savior. So, the Cr48 comes with ChromeOS. With the developer switch turned on, however, you get to do things. Like get access to a real shell. or install a distro like Ubuntu. I didn't want to install Ubuntu on it, so I tried to gain access shell.

Booting into Cr48 after enabling the developer mode, I found that hitting Ctrl+Alt+T brought up a shell. Within Chrome, as a tab(!). However, this was the crosh shell,which is limited. I found out that typing in "shell" gives you access to bash & full range of \*nix utilities. So with that, I first grabbed Linux Mint iso using wget. With the ISO downloaded, I made the USB bootable using dd.

dd if=/path/to/mint.iso of=/dev/sdb

Now, I had a bootable USB. Next step, I used the bootable USB to boot into Linux Mint on my Envy. So now, my Envy is alive. So how do I get this to boot/reinstall Windows? I had Windows 7 ISO, I have Linux Mint & can install VirtualBox. So yup - that's what I did.

- Installed VirtualBox
- Created a new VM, installed Windows 7 to the VM
- Booted in to the Windows 7 VM.
- Now in the Windows 7 VM, I used the Windows 8 upgrade tool to download Windows 8 setup & made a bootable USB(I had another USB key, thankfully!)

With a Windows 8 live USB finally available, I managed to do a clean install and finally revive the Envy.

[1]: https://i.imgur.com/NguB4AP.png
