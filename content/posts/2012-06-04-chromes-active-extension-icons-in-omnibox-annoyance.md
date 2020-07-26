---
title: Chrome’s active extension icons in Omnibox annoyance
author: Sathya
type: post
date: 2012-06-04T15:05:45+00:00
url: /2012/06/04/chromes-active-extension-icons-in-omnibox-annoyance/
topsy_short_url:
  - https://u.sbhat.me/MbxVid
categories:
  - General
tags:
  - browser
  - Chrome
  - Chrome extensions
  - Google Chrome

---
I'm a huge fan of Chrome & pretty much loved whatever changes Chrome team have done to the browser since it's inception. This change, however, is probably the first annoying thing that I've run into.

Few days ago, after the latest dev channel update, all the extension icons on went missing. I initially thought all my extensions got wiped out. However, after heading over to <a href="chrome://extensions" target="_blank">chrome://extensions</a> I realized that the update had a new "Show button" feature next to the extensions list and they had been set to hide all :|

[<img class="alignnone" title="Chrome Extension SHow Button" src="https://i.imgur.com/MBF1a.png" alt="Chrome Extension SHow Button"   />][1]

<!--more-->

Why was it set so, I don't know. Even more annoying is that the favicons of all active extensions on a page will now be placed in the Omnibox. As a result? My omnibox looks like this:<figure style="width: 600px" class="wp-caption alignnone">

[<img class=" " title="Chrome Extension Omnibox" src="https://i.imgur.com/x8hGz.png" alt="Chrome Extension Omnibox"  />][2]<figcaption class="wp-caption-text">Click to view in full</figcaption></figure> 

Talk about useless clutter. I have filed a <a href="https://code.google.com/p/chromium/issues/detail?id=131006" target="_blank">bug for the second behaviour</a>, since I couldn't find an existing bug which talks about this behaviour. Here's a summary of the bug report:

> Chrome Version : 21.0.1155.2
  
> OS Version: 6.1 (Windows 7, Windows Server 2008 R2)
  
> **URLs (if applicable) :**
  
> **Other browsers tested:**
  
> **Add OK or FAIL after other browsers where you have tested this issue:**
  
> Safari 5: N/A
  
> Firefox 4.x: No
  
> IE 7/8/9: N/A
> 
> **What steps will reproduce the problem?**
  
> 1. Install extensions which are active on most pages(Ex: Lazarus, Buffer, RSS Extension, LastPass, ATD, Explain and Send screenshots
  
> 2. Visit the website
> 
> **What is the expected result?**
  
> Omnibox should be free of active extension icons
> 
> **What happens instead?**
  
> Active Extension Icons clutter omnibox
> 
> **Please provide any additional information below. Attach a screenshot if**
  
> **possible.**
> 
> IMO active omnibox icons do not offer much to a user; I don't see why that's required. Especially on sites where lots of extensions are installed.
  
> Add to the mix the fact that userscripts with generic icons are also shown add to the clutter while adding no functionality.
> 
> <a href="https://i.imgur.com/x8hGz.png" rel="nofollow">https://i.imgur.com/x8hGz.png</a>
> 
> My request is to remove the icons being shown in Omnibox. If not, have
  
> a feature where I can hide the active extension icons; much like how "Show button" feature is present for extensions
> 
> <a href="https://i.imgur.com/MBF1a.png" rel="nofollow">https://i.imgur.com/MBF1a.png</a>
> 
> UserAgentString: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.1 (KHTML, like Gecko) Chrome/21.0.1155.2 Safari/537.1

Consider starring the bug in case this behaviour annoys you.

 [1]: https://i.imgur.com/MBF1a.png
 [2]: https://i.imgur.com/x8hGz.png
