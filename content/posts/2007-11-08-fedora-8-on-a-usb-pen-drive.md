---
title: Fedora 8 on a USB pen drive
author: Sathya
type: post
date: 2007-11-08T07:59:51+00:00
url: /2007/11/08/fedora-8-on-a-usb-pen-drive/
categories:
  - News
tags:
  - boot
  - cat
  - Command-line
  - DE
  - Desktop
  - distro
  - download
  - Fedora
  - hard disk
  - IM
  - images
  - install
  - laptop
  - LiveCD
  - mount
  - move
  - owner
  - pen drive
  - read
  - root
  - software
  - usb
  - USB pen drive
  - write
  - yum

---
Fedora’s Project Leader writes on the steps for installing Fedora 8 onto a USB pen drive, making it  bootable Live-drive.  He states,

> I have used a USB key as the _boot device_, and the laptop is currently running [Fedora 8][1], codenamed “[Werewolf][2].” <a id="more-545"></a>
> 
> When I am finished, I can unplug the USB key, power off the machine, and hand the laptop back to its owner. I’ll have my entire distro in my pocket, and when the laptop’s rightful owner powers it back on, the computer will behave as always.
> 
> The following walkthrough will enable you to run Fedora 8 from a USB key.
> 
> ### 0. Prerequisites
> 
> In order to complete this walkthrough, you need:
> 
>   * a computer with Fedora 7 or Fedora 8 installed on it.
>   * root access on that computer.
>   * basic command-line knowledge.
> 
> Steps:
> 
> ### 1. Acquire a USB key
> 
> The basic desktop version of Fedora 8 will fit on a 1 GB USB key. The “developer” version of Fedora 8 will require a 2 GB USB key. Pretty much any brand of USB key should work.
> 
> ### 2. Acquire a Live image
> 
> The Fedora Project releases both _live_ and _installable_ images of the Fedora distribution. In order to run off of a USB key, you need one of the live images — this means that the entire distribution is loaded into the computer’s memory and runs without touching the hard disk at all.
> 
> [Download a live image][3] or [create your own][4] if you are particularly adventurous!
> 
> ### 3. Install livecd-tools
> 
> On your current Fedora machine, install the **livecd-tools** package, either via the graphical
  
> add/remove software application or by using yum directly on the command line. Note that this step requires you to have root access!
> 
> <pre>su -c 'yum install livecd-tools'</pre>
> 
> ### 4. Figure out where your USB key is mounted
> 
> Plug in your USB key and the system should automatically mount it for you. 

[Continue Reading][5]

 [1]: https://fedoraproject.org/wiki/Releases/8/ReleaseSummary
 [2]: https://fedoraproject.org/wiki/Releases/Names
 [3]: https://fedoraproject.org/get-fedora
 [4]: https://www.redhatmagazine.com/2007/05/31/remixing-fedora-7/
 [5]: https://www.redhatmagazine.com/2007/11/07/i-am-fedora-and-so-can-you/
