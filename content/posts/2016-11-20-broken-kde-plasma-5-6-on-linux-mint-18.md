---
title: Broken KDE Plasma 5.6 on Linux Mint 18
author: Sathyajith Bhat
type: post
date: 2016-11-20T13:33:09+00:00
url: /2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/
categories:
  - Opinions
tags:
  - KDE

---
I've been a long time KDE user, loved the KDE 4.0 SC when it first arrived and probably one of the most vocal supporters for it when people were hating it. Since my recent job move, I've been using Linux desktop full-time. Since Linux Mint 18 was the only distro which supported WiFi/Display/Multi-monitor/HDMI out on my Lenovo E41-80(which comes with Skylake chipset), I stuck to it with the Cinnamon desktop.

I decided to check out KDE 5.6 - and installed after adding the PPA backports

> <pre>sudo add-apt-repository ppa:kubuntu-ppa/backports</pre>
> 
> <pre>sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get install kubuntu-desktop</pre>

That should have been it.. and mostly was. Except when I logged out and logged in, I see that my multi-monitor setup is now in mirrored screen mode. A 1080p screen being set to 1366&#215;768 resolution is just plain ugly. There seemed to be no way to change this - I couldn't find a way to reconfigure the screens. Then I realized the application for configuring monitors was not installed - why? I don't know. After bit of fumbling and not knowing which application to install(it's been awhile since I looked at KDE), **I had to launch Synaptic, click on KDE and basically read through description of most applications before realizing it's kscreen which handles multi-monitor setups.** With this installed, finally I was able to set the proper resolution and I spent some more time digging through the settings, setting up shortcuts and stepped away for lunch, When I came back, I was greeted with this screen.

[<img class="aligncenter size-full wp-image-1476" src="https://i.sathyabh.at/ss/2016/10/loginctl-unlock-sessions.jpg" alt="loginctl-unlock-sessions"   />][1]

Flabbergasted, I did as it said, and yep it unlocked fine. After wasting a lot of time going through innumerable posts, I still haven't managed to fix this. I cannot believe this is in a release. Sheesh. This isn't the only instance where KDE Plasma crapped out - multi-monitor is an incredibly unreliable state. From the earlier situation of the multi-manager package not installed to Plasma forgetting your carefully configured desktop settings - it's just big mess.

It's happened on more than one occasion that I open my laptop screen, resuming it from sleep where Plasma instead of restoring the state, just craps out with a black screen and the mouse pointer doesn't even move beyond the first pixel. Only solution: Either kill the X server or switch to different VT and either start a new X session(where if you select Plasma as the DE, you'll be returned  to the broken state) or just restart your system completely(and hope that you haven't setup auto login, because if you and if you login to Plasma - guess what? ye, broken mess). The <a href="https://askubuntu.com/questions/614447/black-screen-after-login-kubuntu-15-04" target="_blank">only "solution" for this</a> is to wipe out your .kde, .config and few other hidden directories which means having to set up from scratch again. Which I did, only to be bitten with the black desktop bug.

I'm done with Plasma for now, I'll return to Cinnamon. Maybe will try it later. Or not.

_<sup>*inb4 your an idiot for using backports, yadda, yadda</sup>_

&nbsp;

 [1]: https://i.sathyabh.at/ss/2016/10/loginctl-unlock-sessions.jpg
