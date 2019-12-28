---
title: Linux problems with solutions
author: Sathya
type: post
date: 2007-10-14T14:30:09+00:00
url: /2007/10/14/linux-problems-with-solutions/
categories:
  - News
tags:
  - /dev
  - AA
  - addon
  - AIR
  - Apache
  - applications
  - apps
  - AWN
  - bin
  - BIOS
  - blog
  - boot
  - browser
  - cat
  - chipset
  - Chrome
  - compiling
  - console
  - crap
  - DE
  - Debian
  - delete
  - Desktop
  - disk usage
  - download
  - driver
  - drivers
  - DVD
  - exe
  - exits
  - ext2
  - ext3
  - FAQ
  - FAT
  - fdisk
  - file
  - find
  - free
  - fsck
  - fun
  - Gentoo
  - Google
  - gtk
  - HAL
  - Home
  - IM
  - images
  - indic
  - install
  - irc
  - iso
  - KDE
  - Koala
  - Konqueror
  - linux
  - login
  - Master
  - media
  - menu
  - mount
  - mounting
  - Mplayer
  - multimedia
  - net
  - New
  - os
  - partition
  - plugin
  - preview
  - Qt
  - read
  - record
  - review
  - Reviews
  - RIA
  - rm
  - RSS
  - Screen
  - script
  - shell
  - shell script
  - show
  - smart
  - Solaris
  - Sun
  - support
  - tar
  - theme
  - themes
  - TV
  - Ubuntu
  - UNIX
  - update
  - updating
  - usb
  - user
  - ux
  - views
  - wallpaper
  - web
  - WINE
  - write
  - X
  - xorg

---
Found this blog while surfing. Very useful!

These are some various linux/unix problems I&#8217;ve encountered over the years, but which I was not able to find a solution for online. Hopefully this will save you the trouble I had.
  
by Vidar Holen
  
[Homepage][1]

[][1]**Problem:**
  
Network interface (or anything else on the pci bus) says &#8220;SIOCSIFFLAGS: Resource temporarily unavailable&#8221;
  
**Cause:** 
  
No IRQ assigned to the device, check /proc/pci (irq says 0)
  
**Solution:** 
  
Enter the bios setup (F1 or Del on boot), disable the option &#8216;Plug n Play OS&#8217;.
  
**Reason:** 
  
This will make your bios set up IRQs for you.

**Problem:**
  
USB mouse using /dev/psaux, the ps/2 mouse device.
  
**Cause:** 
  
Bios usb legacy support in action, probably because Linux didn&#8217;t probe for USB devices (which causes the bios to release control of them).
  
**Solution:** 
  
Compile the kernel with USB support, Input Core and USB HID.
  
**Reason:** 
  
Duh.

**Problem:**
  
USB mouse still doesn&#8217;t work on /dev/input/mice, but /dev/psaux, even when USB support is compiled in.
  
**Cause:** 
  
Legacy USB support again. You might not have compiled in support for your USB chipset (the UHCI parts in USB support).
  
**Solution:** 
  
Compile UHCI. If not working, try the alternate drivers.
  
**Reason:** 
  
Duh.

<!--more-->

**Problem:**
  
Accidentally cat&#8217;ing a binary file causes the all the characters you type next to show up as odd symbols.
  
**Cause:**
  
The binary file contained a 016 (so, Shift Out) character.
  
**Solution:**
  
Print a 017 (Shift In) character. You can use `echo -ne "\\017"` to do this. Even better, make it a shell script called &#8216;fix&#8217; for easy access.
  
**Reason:**
  
Shift Out is canceled by a Shift In.

**Problem:**
  
You scanned an ext3 file system with fsck.ext2/e2fsck, and now you can&#8217;t boot.
  
**Cause:**
  
fsck.ext2 deleted the journaling inode, essentially making it an ext2 fs.
  
**Solution:**
  
Either use `tune2fs -j device` to add the journal node again, or use [c]fdisk to set the partition type to ext2 instead of ext3.
  
**Reason:**
  
tune2fs -j will fix the fs back to ext3 journaling mode, cfdisk will have the system use it as unjournaled ext2.

**Problem:**
  
Some program (especially older ones like RealPlayer, and other multimedia tools/players) hangs when loading, or give a message like &#8220;Can&#8217;t open audio device /dev/dsp: Resource temporarily unavailable.&#8221; or &#8220;No Sound&#8221;
  
**Cause:**
  
Trying to open /dev/dsp (the sound device), but it&#8217;s busy already taken so the program waits or fails.
  
**Solution:**
  
Kill whatever might be hogging it, like artsd. You can find the specific PID using `fuser /dev/dsp`.
  
**Reason:**
  
The app will now have exclusive sound access, and will load without waiting for the device to be free.

**Problem:**
  
Lilo doesn&#8217;t boot your new kernel, giving you odd boot signature messages.
  
**Cause:**
  
It can&#8217;t find the 0xAA55 byte at the end of the boot sector, probably because you didn&#8217;t run &#8216;lilo&#8217; after updating lilo.conf or replacing the kernel file.
  
**Solution:**
  
Run lilo. Get a rescue floppy if needed.
  
**Reason:**
  
Lilo will now store the correct abs disk location for the kernels.

**Problem:**
  
The localhost loopback address 127.0.0.1 doesn&#8217;t work, and so some servers stop functioning and you can only connect to yourself through your lan address.
  
**Cause:**
  
The lo interface might not be configured right.
  
**Solution:**
  
Run &#8220;ifconfig lo up 127.0.0.1&#8221;
  
**Reason:**
  
The loopback interface should now be up and configured with the standard loopback address.

**Problem:**
  
CUPS printer claim to be ready, but is turned off when you start a job, and deletes the job when you start the printer.
  
**Cause:**
  
You&#8217;ve upset the manual gods.
  
**Solution:**
  
Curse, read the manual, delete all the cups files, read the manual, download and compile cups, read the manual, try again.
  
**Reason:**
  
The manual gods will be happy with your sacrifice and will allow you to print (worked for me atleast :)

**Problem:**
  
When using the disk kupdated hogs the cpu, making the system slow to a crawl. The mouse stops responding for several seconds at a time. Serial comm gives errors like &#8220;/dev/ttyS0: 1 input overrun(s)&#8221;.
  
**Cause:**
  
Slow IDE throughput due to unsupported chipset. Run &#8216;hdparm -t /dev/hda&#8217; to make sure (it will be really low, around 2-6mb/s)
  
**Solution:**
  
Compile a kernel that supports your IDE chipset (just enable them all).
  
**Reason:**
  
<sholom> koala_man: Btw, the &#8216;reason&#8217; part for the &#8216;kupdated hogs CPU because of disk usage&#8217; thing is because the system runs in PIO mode, meaning the main CPU have to manage all reading and writing, rather than letting the chipset use busmastering.

**Problem:**
  
Konqueror doesn&#8217;t show gif images.
  
**Cause:**
  
No gif support in QT
  
**Solution:**
  
Edit $QTDIR/src/kernel/qgif.h, define QT\_BUILTIN\_GIF_READER as 1 (tiny file, plenty of comments). configure with -qt-gif. No need to recompile konqueror.
  
**Reason:**
  
The QT library now supports gif, and konqueror can use it.

**Problem:**
  
GTK apps like gimp and xchat suddenly got disgusting fonts.
  
**Cause:**
  
Something changed the settings, possibly an install of another gtk version.
  
**Solution:**
  
Make a ~/.gtkrc file:

<pre>style "user-font"

 {

         font="-misc-fixed-medium-r-normal-*-14-*-*-*-c-*-iso8859-1"

 }

 widget_class "*" style "user-font"</pre>

Replace the font if that doesn&#8217;t suit you.
  
**Reason:**
  
A new default font is now set, instead of the ugly previous one.**Problem:**
  
Konqueror is slow when browsing FTP sites.
  
**Cause:**
  
The icon preview feature occupies the connection, forcing a relogin when changing directories.
  
**Solution:**
  
Uncheck &#8216;ftp&#8217; in the KDE Control Center under Previews in File Manager.
  
**Reason:**
  
Konqueror will now use the connection it made for browsing, rather than showing icon previews.

**Problem:**
  
When starting Half-Life in Wine, a message comes up saying &#8220;Could not open MCI file for playback: 279: Cannot use &#8216;all&#8217; as the device name with the specified command&#8221;
  
**Cause:**
  
Dunno.
  
**Solution:**
  
Run as &#8220;wine hl.exe &#8212; -console&#8221;
  
**Reason:**
  
No clue.

**Problem:**
  
Half-Life in Wine has no sound.
  
**Cause:**
  
DirectSound errors?
  
**Solution:**
  
Try setting voice_enable &#8220;0&#8221; in config.cfg
  
**Reason:**
  
No clue, but it worked for me.

**Problem:**
  
When running Half-Life in Wine, pressing Tab causes the screen to go black (but displays &#8220;Half-Life&#8221; in the left corners).
  
**Cause:**
  
Locked up Alt key perhaps
  
**Solution:**
  
Click somewhere, then click the top left corner. Press Escape then Resume Game. Then hit Alt.
  
**Reason:**
  
I guess the game didn&#8217;t get the alt-release keycode.

**Problem:**
  
Sendmail ignores aliases in /etc/mail/aliases, even after sighups.
  
**Cause:**
  
Sendmail reads from a database, not that file.
  
**Solution:**
  
Use the `-bi` option (or even better, run `newaliases`).
  
**Reason:**
  
It&#8217;ll update the database (/etc/mail/aliases.db).

**Problem:**
  
KMail&#8217;s menu bar is missing.
  
**Cause:**
  
I dunno, messing with styles and themes possibly.
  
**Solution:**
  
Set `MenuBar=Disabled` in <filename>~/.kde/share/config/kmailrc</filename> to, yes, Enabled.
  
**Reason:**
  
I didn&#8217;t see any way of turning it through the gui, so I did it manually.

**Problem:**
  
Mounting of NFS shares is slow, taking exactly five minutes.
  
**Cause:**
  
Not quite sure.
  
**Solution:**
  
Install Portmap on <u>both</u> client and server.
  
**Reason:**
  
I don&#8217;t know.

**Problem:**
  
Apache&#8217;s mod_proxy won&#8217;t allow CONNECTs on vhosts.
  
**Cause:**
  
I think the manual lies. Mod_proxy doesn&#8217;t seem to like vhosts.
  
**Solution:**
  
Make it server wide.
  
**Reason:**
  
Cow.

**Problem:**
  
Can&#8217;t figure out how to whitelist sites using Apache proxies (but can blacklist with ProxyBlock)
  
**Cause:**
  
Not pondering long enough.
  
**Solution:**

<pre>&lt;Directory proxy:*&gt;

    Order Deny,Allow

    Deny from all

    &lt;/Directory&gt;    &lt;Directory proxy:vidarholen.net&gt;

    Order Allow,Deny

    Allow from all

    &lt;/Directory&gt;</pre>

**Reason:**
  
That&#8217;s just the way it is.**Problem:**
  
nvtv only gives black/white output (on an old TV using an s-video to scart converter).
  
**Cause:**
  
Cheap converter
  
**Solution:**
  
Set the Connector to Convert.
  
**Reason:**
  
Quoth the faq, &#8220;You have a SVideo (S-VHS) to Composite connector that uses only the luminance (Y) line of the SVideo connection.&#8221;

**Problem:**
  
Quick access to the konqueror options for changing browser identification and enabling/disabling Java/plugins/javascript not present in the Tools menu.
  
**Cause:**
  
These are additional plugins not present in all default installs.
  
**Solution:**
  
Install konq-plugins in debian, or the kde addons module from the source tree.
  
**Reason:**
  
Duh.

**Problem:**
  
Can&#8217;t make KDE display an html web page as desktop background wallpaper. (Redundant wording for google&#8217;s pleasure)
  
**Solution:**
  
`kwebdesktop`

**Problem:**
  
Neverwinter Nights crashes [on debian], giving only &#8220;Error&#8221; as a message.
  
**Cause:**
  
Running in 16bit mode.
  
**Solution:**
  
Run X in 24bit mode.
  
**Reason:**
  
I don&#8217;t know, gdb indicates a libGLU issue.

**Problem:**
  
Irssi or anything else just hangs, and Ctrl+Q doesn&#8217;t fix it. And you&#8217;re using screen.
  
**Cause:**
  
Screen has an [ES]TX feature too. Perhaps you managed to trigger it.
  
**Solution:**
  
Ctrl-A Q
  
**Reason:**
  
Makes screen write stuff again.

**Problem:**
  
The Cisco vpnclient says &#8220;Could not attach to driver. Is kernel module loaded?&#8221;, and yes, the module&#8217;s loaded.
  
**Cause:**
  
Nowhere to route packets.
  
**Solution:**
  
Check that your nic is listed in ifconfig (if it&#8217;s not and it&#8217;s usb, try [re]loading usb-ohci or ohci-hcd). And up it with dhcpcd or something.
  
**Reason:**
  
Now it can connect.

**Problem:**
  
atitvout says &#8220;VBE call failed&#8221;, esp on Radeon Mobility 7500 (M7 LW).
  
**Cause:**
  
Something about the card not detecting tv-out by itself.
  
**Solution:**
  
Turn the box off. Plug in TV-out. Boot. Start X, and put it in 640&#215;480 (or 800&#215;600). atitvout auto pal; atitvout -f t
  
**Reason:**
  
The card will sense the TV and allow you to turn on tv output.

**Problem:**
  
DVD playing using mplayer and TV-out sucks. With mplayer -vo xv, only the top half of the image is shown. With x11 it only occupies a small area, and with -zoom it runs crap slow and the interlacing is just awful.
  
**Cause:**
  
Dunno
  
**Solution:**
  
Set X to 640&#215;480, mplayer -noframedrop -vo x11 -fs file
  
**Reason:**
  
Dunno, but it looks really great.

**Problem:**
  
UXterm doesn&#8217;t show bold fonts (or xterm with wideChars (-wc))
  
**Solution:**
  
Set a wideFont ala &#8220;xterm\*VT100\*wideFont: -efont-biwidth-medium-r-\*-\*-14-\*-\*-\*-\*-\*-\*-*&#8221;

**Problem:**
  
Compiling irssi says &#8220;/bin/sh: 0: not found&#8221; (OpenBSD).
  
**Solution:**
  
Does your locale exist? Try unsetting all the LC_* variables, configure and make again.

**Problem:**
  
IMAP (imaps) hangs in kmail.
  
**Cause:**
  
kdelibs built without SSL, the imaps kioslave is built but just hangs.
  
**Solution:**
  
Recompile with ssl.

**Problem:**
  
Gentoo says &#8220;* error scanning /etc&#8221; whenever emerge does something.
  
**Cause:**
  
&#8216;find /etc&#8217; said modules.conf was there, but wasn&#8217;t there. An xfs corruption, obviously.
  
**Solution:**
  
I booted from a rescue cd and did xfs_repair. Everything worked smoothly after that.

**Problem:**
  
(ok, so this isn&#8217;t linux) On Solaris on a sun-ray thin client, xlocks locks the screen when you pull out the smart card and I want to change or disable this.
  
**Solution:**
  
Kill your existing utaction process, and/or start a new one with the desired action in -d. (`/opt/SUNWut/lib/utaction -d command`). Also note the -e if you want the action to only run once.

**Problem:**
  
(Solaris again) While compiling OpenGL applications using GLU on solaris, linking failes with Undefined symbol: \_\_1cG\_\_CrunKpure\_error6F\_v_ \_\_1cG\_\_CrunMex\_rethrow\_q6F\_v\_ c::c(N6, (int0\_t)) c::c(N6, (int0\_t)), ld: fatal: Symbol referencing errors. No output written to fluffy
  
**Cause:**
  
GLU requires libCrun which in turn requires libstdc++.
  
**Solution:**
  
Link with both these libs, -lCrun -lstdc++

**Problem:**
  
Cinelerra just hangs with a blank window titled &#8220;x&#8221;.
  
**Solution:**
  
Try it in another wm. Or for Ion, use a FloatWS.

**Problem:**
  
Getting accelerated X-video output on a UniChrome Pro CN700 on Ubuntu 7.04 (Feisty Fawn) on an EPIA EN12000EG for TV-out playback.
  
**Solution:**
  
As of 2007-05-11, OpenChrome supports the CN700 in svn (but not in the stable release). Get and compile the driver (requires automake1.9, not the fancy new stuff), replace via_drv.so in /usr/lib/xorg/modules/drivers with the OpenChrome one. Optionally load the &#8216;drm&#8217; and &#8216;via&#8217; kernel modules. Then configure X to use the &#8216;via&#8217; driver. Here&#8217;s my [xorg.conf][2], for a widescreen PAL TV. Hope you have an easier time than I did.

**Problem:**
  
irrecord fails on lirc 0.8.2, with kernel 2.6.22.1. It when a button is pressed, it exits immediately but claims &#8220;irrecord: no data for 10 secs, aborting, irrecord: gap not found, can&#8217;t continue&#8221;
  
**Solution:**
  
lirc 0.8.2 doesn&#8217;t support this kernel (it&#8217;s probably fixed in the latest version by the time you read this). Downgrade to 2.6.20 and it works like a charm.

 [1]: http://www.vidarholen.net/
 [2]: http://www.vidarholen.net/contents/linuxtips/xorg.conf