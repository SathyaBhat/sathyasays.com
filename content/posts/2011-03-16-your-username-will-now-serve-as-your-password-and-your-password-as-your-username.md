---
title: Your Username Will Now Serve as Your Password and Your Password as Your Username
author: Sathya
type: post
date: 2011-03-16T16:59:30+00:00
url: /2011/03/16/your-username-will-now-serve-as-your-password-and-your-password-as-your-username/
topsy_short_url:
  - http://u.sbhat.me/eqfAlf
categories:
  - News
tags:
  - security
  - SQL Injection
  - website

---
You might have read this on Hacker News/reddit, but still, this is too much of a WTF NOT to share.

Basically, if you try to login to Caledonian Record, &#8211; a St. Johnsbury, Vermont based media website <a href="http://news.ycombinator.com/item?id=2329758" target="_blank">which</a>

> <span style="font-family: Verdana; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px; line-height: normal;">recently put the site behind a pay wall and I can no longer catch up on hometown news</span>

<span style="font-family: Verdana;"><span style="line-height: normal; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;">you get an &#8220;announcement&#8221; of epic proportions</span></span>

> RETURNING CUSTOMERS, PLEASE NOTE THE FOLLOWING SECURITY CHANGE: YOUR USERNAME WILL NOW SERVE AS YOUR PASSWORD AND YOUR PASSWORD WILL NOW SERVE AS YOUR USERNAME

\*facepalm\*.

[&#8220;Icing&#8221; on the cake?][1]

> <span style="font-family: Verdana; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px; line-height: normal;">Not unsurprisingly, x&#8217; AND email IS NULL; &#8212; works as the username with no password. Injection FTL.</span>
> 
> <span style="font-family: Verdana; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px; line-height: normal;"><span>It seems like any username that includes a semicolon at any point will authenticate</span></span>

<span style="font-family: Verdana; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px; line-height: normal;"><span>Security change, indeed.</span></span>

via [Hacker News | Your Username Will Now Serve as Your Password and Your Password as Your Username][2].

 [1]: http://news.ycombinator.com/item?id=2330309
 [2]: http://news.ycombinator.com/item?id=2329366