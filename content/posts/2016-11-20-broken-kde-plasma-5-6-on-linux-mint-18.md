---
title: Broken KDE Plasma 5.6 on Linux Mint 18
author: Sathya
type: post
date: 2016-11-20T13:33:09+00:00
url: /2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/
categories:
  - Opinions
tags:
  - KDE
  - Mint 18
  - plasma

---
I&#8217;ve been a long time KDE user, loved the KDE 4.0 SC when it first arrived and probably one of the most vocal supporters for it when people were hating it. Since my recent job move, I&#8217;ve been using Linux desktop full-time. Since Linux Mint 18 was the only distro which supported WiFi/Display/Multi-monitor/HDMI out on my Lenovo E41-80(which comes with Skylake chipset), I stuck to it with the Cinnamon desktop.

I decided to check out KDE 5.6 &#8211; and installed after adding the PPA backports

> <pre>sudo add-apt-repository ppa:kubuntu-ppa/backports</pre>
> 
> <pre>sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get install kubuntu-desktop</pre>

That should have been it.. and mostly was. Except when I logged out and logged in, I see that my multi-monitor setup is now in mirrored screen mode. A 1080p screen being set to 1366&#215;768 resolution is just plain ugly. There seemed to be no way to change this &#8211; I couldn&#8217;t find a way to reconfigure the screens. Then I realized the application for configuring monitors was not installed &#8211; why? I don&#8217;t know. After bit of fumbling and not knowing which application to install(it&#8217;s been awhile since I looked at KDE), **I had to launch Synaptic, click on KDE and basically read through description of most applications before realizing it&#8217;s kscreen which handles multi-monitor setups.** With this installed, finally I was able to set the proper resolution and I spent some more time digging through the settings, setting up shortcuts and stepped away for lunch, When I came back, I was greeted with this screen.

[<img data-attachment-id="1476" data-permalink="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/loginctl-unlock-sessions/" data-orig-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2016/10/loginctl-unlock-sessions.jpg?fit=1280%2C960&ssl=1" data-orig-size="1280,960" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="loginctl-unlock-sessions" data-image-description="" data-medium-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2016/10/loginctl-unlock-sessions.jpg?fit=608%2C456&ssl=1" data-large-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2016/10/loginctl-unlock-sessions.jpg?fit=740%2C555&ssl=1" class="aligncenter size-full wp-image-1476" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2016/10/loginctl-unlock-sessions.jpg?resize=740%2C555&#038;ssl=1" alt="loginctl-unlock-sessions" width="740" height="555" data-recalc-dims="1" />][1]

Flabbergasted, I did as it said, and yep it unlocked fine. After wasting a lot of time going through innumerable posts, I still haven&#8217;t managed to fix this. I cannot believe this is in a release. Sheesh. This isn&#8217;t the only instance where KDE Plasma crapped out &#8211; multi-monitor is an incredibly unreliable state. From the earlier situation of the multi-manager package not installed to Plasma forgetting your carefully configured desktop settings &#8211; it&#8217;s just big mess.

It&#8217;s happened on more than one occasion that I open my laptop screen, resuming it from sleep where Plasma instead of restoring the state, just craps out with a black screen and the mouse pointer doesn&#8217;t even move beyond the first pixel. Only solution: Either kill the X server or switch to different VT and either start a new X session(where if you select Plasma as the DE, you&#8217;ll be returned  to the broken state) or just restart your system completely(and hope that you haven&#8217;t setup auto login, because if you and if you login to Plasma &#8211; guess what? ye, broken mess). The <a href="http://askubuntu.com/questions/614447/black-screen-after-login-kubuntu-15-04" target="_blank">only &#8220;solution&#8221; for this</a> is to wipe out your .kde, .config and few other hidden directories which means having to set up from scratch again. Which I did, only to be bitten with the black desktop bug.

I&#8217;m done with Plasma for now, I&#8217;ll return to Cinnamon. Maybe will try it later. Or not.

_<sup>*inb4 your an idiot for using backports, yadda, yadda</sup>_

&nbsp;

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1468" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1468" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1468" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2016/11/20/broken-kde-plasma-5-6-on-linux-mint-18/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: https://i1.wp.com/sathyasays.com/wp-content/uploads/2016/10/loginctl-unlock-sessions.jpg?ssl=1