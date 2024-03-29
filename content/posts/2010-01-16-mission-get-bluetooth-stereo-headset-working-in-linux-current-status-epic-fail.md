---
title: 'Mission: Get Bluetooth Stereo Headset Working in Linux. Current Status: EPIC FAIL'
author: Sathyajith Bhat
type: post
date: 2010-01-16T09:41:42+00:00
url: /2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/

categories:
  - "Tips & How-To's"
tags:
  - bluetooth
  - linux

---
I've owned a Sony Ericsson HBH-DS970 for [nearly 2 years now][1] ), and my current iPhone 3G. I also use it occasionally on my laptop. It has worked fine in Windows XP, Vista & Windows 7. Getting it to work with Linux, however has been an EPIC FAIL. The last time I tried it was probably a year ago, and I just gave up in frustration and continued to use my EP-630 as the earphone.



The situation however changed when recently some <span style="text-decoration: line-through;">bloody fucking bastard</span> person [stole my EP-630][3] in office - since I don't have any other headset, I got all "enthu" about trying to get this ting working. And now all that enthusiasm has gone, and I'm on the verge of giving up again. So let me point as to what steps I \*have\* tried.

  * [bluetooth-alsa on SourceForge][4]

Result: FAIL. Couldn't build the required files, couldn't get the required development files - packages do not exist as they have been obsoleted, and the method itself obsoleted.

  * [bluez wiki][5]

Result: FAIL. Configured the .asoundrc file, added hcid.conf files, on testing with mplayer got an error message:

> `[AO_ALSA] alsa-lib: audio/pcm_bluetooth.c:1607:(audioservice_expect) BT_GET_CAPABILITIES failed : Input/output error(5)<br />
[AO_ALSA] Playback open error: Input/output error`

Tried with arecord:

> `sathya@shaman:~> arecord -D bluetooth -f S16_LE | aplay -D bluetooth -f S16_LE<br />
ALSA lib audio/pcm_bluetooth.c:1607:(audioservice_expect) BT_GET_CAPABILITIES failed : Input/output error(5)<br />
arecord: main:608: audio open error: Input/output error<br />
ALSA lib audio/pcm_bluetooth.c:1607:(audioservice_expect) BT_GET_CAPABILITIES failed : Input/output error(5)<br />
aplay: main:608: audio open error: Input/output error`

  * [FOSSwire article: A2DP on Linux][6]

Result: FAIL. Tried their script, seemed to work but no. At the end of script got an error message

> `Starting up...<br />
Traceback (most recent call last): File "a2dp.py", line 7, in bus_id = manager.ActivateService('audio')<br />
dbus.exceptions.DBusException: org.freedesktop.DBus.Error.UnknownMethod: Method "ActivateService" with signature "s" on interface "org.bluez.Manager" doesn't exist` 

The author mentions this error is because this method is now obsolete.

  * [FOSSwire:  Better Bluetooth Audio in Linux][7]

Got stuck when I issued:

> `pactl load-module module-alsa-sink device="bluetooth"`

Error being:

> `<br />
sathya@shaman:~> pactl load-module module-alsa-sink device="bluetooth"<br />
Failure: Module initalization failed`

Slick.

  * [IT Toolbox: Mission Impossble? Connect Bluetooth Headset to Linux][8]

Result: Didn't bother. Same as attempt #2.

I've just about given up trying to get this damn thing working. If you have any suggestions/advice, do drop a comment. FYI: I'm on openSUSE, my headset is a Sony Ericsson HBH DS970.

 [1]: https://sathyabh.at/2008/05/22/my-bt-headset-is-here/
 [2]: https://sathyabh.at/2008/03/30/sony-ericsson-p1i-review/
 [3]: https://twitter.com/sathyabhat/statuses/7403663222
 [4]: https://bluetooth-alsa.sourceforge.net/build.html
 [5]: https://wiki.bluez.org/wiki/HOWTO/AudioDevices
 [6]: https://fosswire.com/post/2008/1/a2dp-stereo-linux/
 [7]: https://fosswire.com/post/2008/10/better-bluetooth-audio/
 [8]: https://it.toolbox.com/blogs/locutus/mission-impossible-connect-bluetooth-headset-to-linux-35365
