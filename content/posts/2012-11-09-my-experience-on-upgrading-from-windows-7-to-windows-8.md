---
title: My Experience on upgrading from Windows 7 to Windows 8
author: Sathya
type: post
date: 2012-11-09T10:24:19+00:00
url: /2012/11/09/my-experience-on-upgrading-from-windows-7-to-windows-8/
categories:
  - Opinions
tags:
  - HP envy
  - windows 8

---
So after much thought, I upgraded my Windows 7 Ultimate install to Windows 8. I didn&#8217;t plan to upgrade so soon, I wanted to wait for few more months before doing the upgrade &#8211; the main reason for holding back the upgrade was lack of drivers. However with <a href="http://superuser.com" target="_blank">Super User</a>&#8216;s [Windows 8 Challenge][1] around, I could no longer use the RP for posting answers.

And since the RP was working fine, including the GPU drivers which I had to install in Windows 7 compatibility mode, I decided to complete the upgrade. Now my Windows 7 install is a culmination of several years of crap, including lots and lots of software, context menu entries, personalized superbar and to add to the mix, some exotic software  Here&#8217;s what I had installed/present on Windows 7

<!--more-->

  * VS 2010 Web Dev edition Express(<a href="http://stackoverflow.com/q/4566908/92837" target="_blank">for nuGet)</a> & VS 2012 Express for Windows Desktop
  * SQL Server 2008
  * SQL Server 2005 Compact edition(I think for Windows Live Photo gallery?)
  * Actual Multiple Monitors ( I have an extended desktop setup, Actual Multiple Monitors makes multiple monitors usable and less frustrating on Windows 7)
  * WinSplit Revolution
  * Connectify(when I&#8217;m in my hometown, there&#8217;s no wireless router there, so the laptop becomes my adhoc Wifi router)
  * Puty, WinSCP
  * Git, Github & Git Extensions(including GitExtensions&#8217; context menu entries)
  * Mercurial & Kiln
  * Media players like xbmc, Media Player Classic: Home Cinema & VLC
  * SublimeText 2
  * IrfanView
  * foobar 2000 (including some plugins &#8211; such as <a href="http://techie-buzz.com/how-to/convert-your-iphoneipod-touch-or-any-wifi-enabled-gadget-to-foobar2000-remote.html" target="_blank">this plugin which makes it possible</a> to control foobar from anywhere)
  * Bunch of scheduled tasks which run <a href="http://www.microsoft.com/en-in/download/details.aspx?id=15155" target="_blank">SyncToy</a> & <a href="http://www.gamesave-manager.com/" target="_blank">GameSaveManager</a> and ensure I have automated daily backups
  * Gaming platforms & tools like <a title="Steam Profile" href="http://steamcommunity.com/id/sathyabhat" target="_blank">Steam</a>, Origin, Raptr and <a href="http://raptr.com/sathyabhat/games" target="_blank">loads of games</a>
  * Dropbox
  * Logitech Gaming Software to manage my Logitech G400 mouse bindings & DPI settings
  * ProcrastiTracker (I&#8217;d been running ProcrastiTracker side-by-side with Wakoopa, which unfortunately was <a href="http://sathyasays.com/2012/07/05/wakoopa-officially-shutdown-grab-your-data-now/" target="_blank">killed</a> quite some time ago)
  * <a href="http://sathyabh.at/2010/02/25/take-a-screenshot-of-your-desktop-and-upload-to-imageshack-easily/" target="_blank">Some extra tools</a> I wrote to make my life easy, esp <a href="https://github.com/SathyaBhat/StackEd" target="_blank">when editing stuff</a> on Stack Exchange
  * Networx
  * Teracopy
  * <a title="System Mechanic Review" href="http://techie-buzz.com/reviews/system-mechanic-10-8-review.html" target="_blank">SystemMechanic</a>

And these are just some apps that I use regularly &#8211; there&#8217;s loads of more such apps that I won&#8217;t get into details right now.

Much like a lot of people, I grabbed the Windows 8 upgrade assistant, and left it overnight to complete the download. The Upgrade assistant has a <s>funny</s> stupid behaviour where if <a href="http://superuser.com/q/495537/4377" target="_blank">you quit the upgrade assistant before you hit the pause button</a>, it conveniently decides to delete whatever it&#8217;s downloaded till that point.

So if you&#8217;ve grabbed 99.9% of the file and if you quit the assistant before you hit the Pause button &#8211; well then shit, all that download is gone. So moral of the story: Pause before you quit.

That hiccup aside, I left the Upgrade assistant overnight to complete the download. Next morning, I started the upgrade and left for work. Back from work, I see that Windows 8 is ready for me, asking me for some details (&#8220;which colour do you want?&#8221;) and prompted me to create an account(though I already had an account from the Windows 7 install). Thankfully, it proceeded to merge things with the existing account.

So how did my system look after the upgrade? **Amazingly, for all the crap I had on my system, the upgrade went exceedingly well. No broken programs, no broken links, for that matter all my scheduled tasks, context menu entries, startup items, superbar entries all were preserved.**

What was broken, however, was my multi-monitor setup. My HP envy has a hybrid IGP-discrete GPU setup. The IGP is an Intel HD graphics thing, while the discrete GPU is an AMD Radeon Mobility 5650.

Post Windows 8 upgrade, I noticed that both the IGP as well as the GPU had been using Microsoft&#8217;s built-in drivers. While IGP drivers were working fine, the GPU drivers were borked and it was not being detected.

[<img class="aligncenter" src="http://i.stack.imgur.com/jiQdJ.png" alt=""   />][2]

I tried to use the previous Windows 7 drivers, running them under Windows 7 compatibility mode, but the install would silently fail. Taking a look at the logs, I see that the install failed because the installer kept throwing <a href="http://chat.stackexchange.com/transcript/118?m=6771791#6771791" target="_blank">ACCESS_VIOLATION errors in the MFC dlls</a>. With a little rubber-duck debugging help from Root Access, some VS 2005 runtime uninstalls, and a <a href="http://archive.msdn.microsoft.com/KB961894/Release/ProjectReleases.aspx?ReleaseId=2067" target="_blank">hotfix install</a> I managed to get the install running. The drivers still managed to fail installation &#8211; the drivers were dated back to 2010 and Windows refused to install the older drivers.

Finally after a lot of wrangling around, I downloaded AMD&#8217;s beta drivers(which don&#8217;t seem to have the check for &#8220;supported chipsets&#8221;, as opposed to the stable drivers and managed to get it installed. (thanks to <a href="https://twitter.com/TheRomit/status/265496483422429184" target="_blank">Romit for the tip</a>).

Now I do have my extended desktop running, but being the beta drivers that they are, I&#8217;ve run into several driver crashes(thankfully since Vista or so, GPU driver crash no longer brings about a BSOD). And worst of all, my system believes there are 3 monitors

[<img class="alignnone" src="http://i.stack.imgur.com/OVi9F.png" alt=""   />][3]

This is a pain because I use Actual Multiple Monitors which adds 1-click move to next monitor and with the third &#8220;phantom&#8221; monitor, the move to next monitor workflow goes for a toss.

From a software point of view, Raptr reports that they have disabled in-game and tracking features. AMD&#8217;s beta drivers mean that the switchable graphics doesn&#8217;t work. I don&#8217;t think I&#8217;ve run into other problems

### Thoughts on Windows 8

Still too early to judge Windows 8 for now &#8211; I do like the Modern UI & how Microsoft has conceptualized it, but ultimately, Modern UI apps are bit too restrictive for my taste, especially when I have multiple programs running simultaneously  and each app dedicated it&#8217;s own space on my monitor(via WinSplitRevolution) &#8211; the Modern UI doesn&#8217;t allow for this and I keep having to go back to desktop mode more often than not.

As for Modern UI apps, I haven&#8217;t tried too many. I like the People hub/app. Youtube RT is pretty nifty, esp for having it on the small screen, with a twitter or the messaging app in the snapped view. Things like this is where Modern UI really shines.

If you&#8217;ve been wondering whether or not to upgrade, I&#8217;d urge you to consider the upgrade. For most people, Modern UI works well, and though the Start Screen is something totally different, you&#8217;ll come up to speed with it in no time.

For powerusers, Win+C & Win+X and the desktop mode should keep you entertained.

(oh, before I forget, #scumbagHP had decided that all laptops sold prior to October 1, 2011 aren&#8217;t going to get driver updates for Windows 8. Sadly mine falls into that category. While I took that risk, i&#8217;d urge you to not do so, for it might lead to frustration).

<blockquote class="twitter-tweet">
  <p>
    meanwhile, HP says they won&#8217;t provide Win 8 drivers for laptops sold before Oct 2011.<a href="http://t.co/ixlSruf6" title="http://u.sbhat.me/VBtDr9">u.sbhat.me/VBtDr9</a> cc @<a href="https://twitter.com/theromit">theromit</a>
  </p>
  
  <p>
    &mdash; Sathya (@SathyaBhat) <a href="https://twitter.com/SathyaBhat/status/266067355786944514" data-datetime="2012-11-07T06:39:35+00:00">November 7, 2012</a>
  </p>
</blockquote>



<blockquote class="twitter-tweet">
  <p>
    &#8220;prior to October 1st , 2011, HP has not tested or developed drivers.upgrade of your computer may be difficult or impossible.&#8221; <a href="https://twitter.com/search/%23scumbagHP">#scumbagHP</a>
  </p>
  
  <p>
    &mdash; Sathya (@SathyaBhat) <a href="https://twitter.com/SathyaBhat/status/266068268274548736" data-datetime="2012-11-07T06:43:13+00:00">November 7, 2012</a>
  </p>
</blockquote>

 [1]: http://win8challenge.com/
 [2]: http://i.stack.imgur.com/jiQdJ.png
 [3]: http://i.stack.imgur.com/OVi9F.png
