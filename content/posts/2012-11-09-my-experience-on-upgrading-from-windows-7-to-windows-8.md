---
title: My Experience on upgrading from Windows 7 to Windows 8
author: Sathyajith Bhat
type: post
date: 2012-11-09T10:24:19+00:00
url: /2012/11/09/my-experience-on-upgrading-from-windows-7-to-windows-8/
categories:
  - Opinions
tags:
  - windows
---

So after much thought, I upgraded my Windows 7 Ultimate install to Windows 8. I didn't plan to upgrade so soon, I wanted to wait for few more months before doing the upgrade - the main reason for holding back the upgrade was lack of drivers. However with <a href="https://superuser.com" target="_blank">Super User</a>&#8216;s Windows 8 Challenge around, I could no longer use the RP for posting answers.

And since the RP was working fine, including the GPU drivers which I had to install in Windows 7 compatibility mode, I decided to complete the upgrade. Now my Windows 7 install is a culmination of several years of crap, including lots and lots of software, context menu entries, personalized superbar and to add to the mix, some exotic software  Here's what I had installed/present on Windows 7

- VS 2010 Web Dev edition Express(<a href="https://stackoverflow.com/q/4566908/92837" target="_blank">for nuGet)</a> & VS 2012 Express for Windows Desktop
- SQL Server 2008
- SQL Server 2005 Compact edition(I think for Windows Live Photo gallery?)
- Actual Multiple Monitors ( I have an extended desktop setup, Actual Multiple Monitors makes multiple monitors usable and less frustrating on Windows 7)
- WinSplit Revolution
- Connectify(when I'm in my hometown, there's no wireless router there, so the laptop becomes my adhoc Wifi router)
- Puty, WinSCP
- Git, Github & Git Extensions(including GitExtensions' context menu entries)
- Mercurial & Kiln
- Media players like xbmc, Media Player Classic: Home Cinema & VLC
- SublimeText 2
- IrfanView
- foobar 2000
- Bunch of scheduled tasks which run SyncToy & GameSaveManager and ensure I have automated daily backups
- Gaming platforms & tools like <a title="Steam Profile" href="https://steamcommunity.com/id/sathyabhat" target="_blank">Steam</a>, Origin, Raptr and loads of games
- Dropbox
- Logitech Gaming Software to manage my Logitech G400 mouse bindings & DPI settings
- ProcrastiTracker (I'd been running ProcrastiTracker side-by-side with Wakoopa, which unfortunately was <a href="https://sathyasays.com/2012/07/05/wakoopa-officially-shutdown-grab-your-data-now/" target="_blank">killed</a> quite some time ago)
- <a href="https://sathyabh.at/2010/02/25/take-a-screenshot-of-your-desktop-and-upload-to-imageshack-easily/" target="_blank">Some extra tools</a> I wrote to make my life easy, esp <a href="https://github.com/SathyaBhat/StackEd" target="_blank">when editing stuff</a> on Stack Exchange
- Networx
- Teracopy

And these are just some apps that I use regularly - there's loads of more such apps that I won't get into details right now.

Much like a lot of people, I grabbed the Windows 8 upgrade assistant, and left it overnight to complete the download. The Upgrade assistant has a <s>funny</s> stupid behaviour where if <a href="https://superuser.com/q/495537/4377" target="_blank">you quit the upgrade assistant before you hit the pause button</a>, it conveniently decides to delete whatever it's downloaded till that point.

So if you've grabbed 99.9% of the file and if you quit the assistant before you hit the Pause button - well then shit, all that download is gone. So moral of the story: Pause before you quit.

That hiccup aside, I left the Upgrade assistant overnight to complete the download. Next morning, I started the upgrade and left for work. Back from work, I see that Windows 8 is ready for me, asking me for some details ("which colour do you want?") and prompted me to create an account(though I already had an account from the Windows 7 install). Thankfully, it proceeded to merge things with the existing account.

So how did my system look after the upgrade? **Amazingly, for all the crap I had on my system, the upgrade went exceedingly well. No broken programs, no broken links, for that matter all my scheduled tasks, context menu entries, startup items, superbar entries all were preserved.**

What was broken, however, was my multi-monitor setup. My HP envy has a hybrid IGP-discrete GPU setup. The IGP is an Intel HD graphics thing, while the discrete GPU is an AMD Radeon Mobility 5650.

Post Windows 8 upgrade, I noticed that both the IGP as well as the GPU had been using Microsoft's built-in drivers. While IGP drivers were working fine, the GPU drivers were borked and it was not being detected.

[<img class="aligncenter" src="https://i.stack.imgur.com/jiQdJ.png" alt=""   />][2]

I tried to use the previous Windows 7 drivers, running them under Windows 7 compatibility mode, but the install would silently fail. Taking a look at the logs, I see that the install failed because the installer kept throwing <a href="https://chat.stackexchange.com/transcript/118?m=6771791#6771791" target="_blank">ACCESS_VIOLATION errors in the MFC dlls</a>. With a little rubber-duck debugging help from Root Access, some VS 2005 runtime uninstalls, and a hotfix install I managed to get the install running. The drivers still managed to fail installation - the drivers were dated back to 2010 and Windows refused to install the older drivers.

Finally after a lot of wrangling around, I downloaded AMD's beta drivers(which don't seem to have the check for "supported chipsets", as opposed to the stable drivers and managed to get it installed. (thanks to <a href="https://twitter.com/TheRomit/status/265496483422429184" target="_blank">Romit for the tip</a>).

Now I do have my extended desktop running, but being the beta drivers that they are, I've run into several driver crashes(thankfully since Vista or so, GPU driver crash no longer brings about a BSOD). And worst of all, my system believes there are 3 monitors

[<img class="alignnone" src="https://i.stack.imgur.com/OVi9F.png" alt=""   />][3]

This is a pain because I use Actual Multiple Monitors which adds 1-click move to next monitor and with the third "phantom" monitor, the move to next monitor workflow goes for a toss.

From a software point of view, Raptr reports that they have disabled in-game and tracking features. AMD's beta drivers mean that the switchable graphics doesn't work. I don't think I've run into other problems

### Thoughts on Windows 8

Still too early to judge Windows 8 for now - I do like the Modern UI & how Microsoft has conceptualized it, but ultimately, Modern UI apps are bit too restrictive for my taste, especially when I have multiple programs running simultaneously  and each app dedicated it's own space on my monitor(via WinSplitRevolution) - the Modern UI doesn't allow for this and I keep having to go back to desktop mode more often than not.

as for Modern UI apps, I haven't tried too many. I like the People hub/app. Youtube RT is pretty nifty, esp for having it on the small screen, with a twitter or the messaging app in the snapped view. Things like this is where Modern UI really shines.

If you've been wondering whether or not to upgrade, I'd urge you to consider the upgrade. For most people, Modern UI works well, and though the Start Screen is something totally different, you'll come up to speed with it in no time.

For powerusers, Win+C & Win+X and the desktop mode should keep you entertained.

(oh, before I forget, #scumbagHP had decided that all laptops sold prior to October 1, 2011 aren't going to get driver updates for Windows 8. Sadly mine falls into that category. While I took that risk, i'd urge you to not do so, for it might lead to frustration).

[2]: https://i.stack.imgur.com/jiQdJ.png
[3]: https://i.stack.imgur.com/OVi9F.png
