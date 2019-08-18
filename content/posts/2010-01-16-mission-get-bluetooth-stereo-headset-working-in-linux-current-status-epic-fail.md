---
title: 'Mission: Get Bluetooth Stereo Headset Working in Linux. Current Status: EPIC FAIL'
author: Sathya
type: post
date: 2010-01-16T09:41:42+00:00
url: /2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/
topsy_short_url:
  - http://bit.ly/4wESPN
categories:
  - News
tags:
  - a2dp
  - ALSA
  - bluetooth
  - bluez
  - commands
  - DE
  - Desktop
  - file
  - FOSS
  - free
  - hassles
  - IM
  - iPhone
  - laptop
  - linux
  - Mplayer
  - openSuSE
  - os
  - record
  - script
  - SUSE
  - tar
  - testing
  - ux
  - Vista
  - windows
  - X
  - xp

---
I&#8217;ve owned a Sony Ericsson HBH-DS970 for [nearly 2 years now][1]{#aptureLink_GW9kUit5Kx}, and I use it pretty often with my previous phone ( the [Sony Ericsson P1i][2]{#aptureLink_Szc3RZREO3} ), and my current iPhone 3G. I also use it occasionally on my laptop. It has worked fine in Windows XP, Vista & Windows 7. Getting it to work with Linux, however has been an EPIC FAIL. The last time I tried it was probably a year ago, and I just gave up in frustration and continued to use my EP-630 as the earphone.

<!--more-->

The situation however changed when recently some <span style="text-decoration: line-through;">bloody fucking bastard</span> person [stole my EP-630][3]{#aptureLink_NSxWrq0F8x} in office &#8211; since I don&#8217;t have any other headset, I got all &#8220;enthu&#8221; about trying to get this ting working. And now all that enthusiasm has gone, and I&#8217;m on the verge of giving up again. So let me point as to what steps I \*have\* tried.

  * [bluetooth-alsa on SourceForge][4]

Result: FAIL. Couldn&#8217;t build the required files, couldn&#8217;t get the required development files &#8211; packages do not exist as they have been obsoleted, and the method itself obsoleted.

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

Result: Didn&#8217;t bother. Same as attempt #2.

I&#8217;ve just about given up trying to get this damn thing working. If you have any suggestions/advice, do drop a comment. FYI: I&#8217;m on openSUSE, my headset is a Sony Ericsson HBH DS970.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-828" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-828" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-828" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/01/16/mission-get-bluetooth-stereo-headset-working-in-linux-current-status-epic-fail/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyabh.at/2008/05/22/my-bt-headset-is-here/
 [2]: http://sathyabh.at/2008/03/30/sony-ericsson-p1i-review/
 [3]: http://twitter.com/sathyabhat/statuses/7403663222
 [4]: http://bluetooth-alsa.sourceforge.net/build.html
 [5]: http://wiki.bluez.org/wiki/HOWTO/AudioDevices
 [6]: http://fosswire.com/post/2008/1/a2dp-stereo-linux/
 [7]: http://fosswire.com/post/2008/10/better-bluetooth-audio/
 [8]: http://it.toolbox.com/blogs/locutus/mission-impossible-connect-bluetooth-headset-to-linux-35365