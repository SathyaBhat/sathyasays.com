---
title: openSUSE’s software manager lists Mono apps under Proprietary Applications Pattern
author: Sathya
type: post
date: 2010-07-10T13:29:13+00:00
url: /2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/
topsy_short_url:
  - http://bit.ly/cW5jZA
categories:
  - General
tags:
  - 1-click install
  - applications
  - apps
  - bin
  - cat
  - community
  - DE
  - DJ
  - IM
  - install
  - linux
  - Mono
  - openSuSE
  - software
  - SUSE
  - tar
  - Unity
  - X
  - YaST
  - zypper

---
<img data-attachment-id="874" data-permalink="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/mono/" data-orig-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?fit=903%2C627&ssl=1" data-orig-size="903,627" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="Mono Apps" data-image-description="" data-medium-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?fit=608%2C422&ssl=1" data-large-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?fit=740%2C513&ssl=1" class="aligncenter size-medium wp-image-874" title="Mono Apps" src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono-608x422.png?resize=608%2C422" alt="" width="608" height="422" srcset="https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?resize=608%2C422&ssl=1 608w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?resize=800%2C555&ssl=1 800w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2010/07/mono.png?w=903&ssl=1 903w" sizes="(max-width: 608px) 100vw, 608px" data-recalc-dims="1" />I&#8217;ve been using openSUSE for quite some time now, but this is definitely the first time that I&#8217;ve noticed this ( though probably because I tend to use zypper or the 1-click install rather than entering YaST).

Edit:
  
Output of `zypper lr -u`
  
<http://pastebin.com/awfeBeLP>

Output of `zypper se -s -i -t pattern`
  
<http://pastebin.com/DJc8HsLG>

Output of `zypper sl -d`
  
<http://pastebin.com/LxLREddG>

Edit 2: [Andreas Jaegar][1]{#aptureLink_6hGvH0hOns} comments on the above:

> Found it: The pattern is part of Mono Community pattern. As these ymp-patterns have no category, the software manager picks a pretty much random order. And it happens to be under proprietary software in this case.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-873" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-873" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-873" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/07/10/opensuses-software-manager-lists-mono-apps-under-proprietary-applications-pattern/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://en.opensuse.org/User:A_jaeger