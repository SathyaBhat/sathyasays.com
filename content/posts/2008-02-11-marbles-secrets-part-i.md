---
title: 'Marble’s Secrets: Part I'
author: Sathya
type: post
date: 2008-02-11T04:41:37+00:00
url: /2008/02/11/marbles-secrets-part-i/
categories:
  - General
tags:
  - blog
  - cat
  - DE
  - Desktop
  - download
  - git
  - GPL
  - Home
  - IM
  - KDE
  - KDE4
  - license
  - linux
  - marbles
  - mount
  - open source
  - Opera
  - Operating System
  - os
  - Qt
  - read
  - show
  - support
  - tar
  - theme
  - themes
  - X

---
If you&#8217;ve ever followed KDE 4 development then you&#8217;ve probably heard about Marble. Marble is a virtual globe which displays the earth. So Marble can be used as a nice digital replacement for your desktop globe at home where you can look up places.

But wait! There&#8217;s more to it: Actually these days Marble can also display flat maps (thanks to Carlos Licea), can show different &#8220;map themes&#8221; and can serve as a Qt4-widget as well as an application! This means that as a programmer you can use Marble in your very own project as a map widget (License: LGPL). _Marble was designed to run on any device and on any operating system supported by Qt4 without any further requirements._ You can download the latest version of Marble together with KDE 4.0.1 [here][1] (It&#8217;s part of the KDE-EDU module).

**How Marble stores texture data**

If you start Marble you might realize that the startup time is pretty good: It usually takes maybe 2-5 secs to start Marble (and we are working on improving that dramatically). If you zoom into the earth you might notice that Marble doesn&#8217;t get slower while zooming in. Looking at the amount of memory being used up you will also see that memory numbers don&#8217;t change either. _No matter how much you zoom in it&#8217;s as little as 65-100MB_ which is pretty lean compared to other virtual globes.
  
Among other concepts this is being accomplished by loading the map piece by piece. Marble uses a concept that is very popular among virtual globes: _Quadtiles_.

Continue reading at [torsten rahn&#8217;s blog][2]

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/02/11/marbles-secrets-part-i/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-254" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/02/11/marbles-secrets-part-i/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-254" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/02/11/marbles-secrets-part-i/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-254" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/02/11/marbles-secrets-part-i/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/02/11/marbles-secrets-part-i/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.kde.org/info/4.0.1.php
 [2]: http://www.kdedevelopers.org/blog/551