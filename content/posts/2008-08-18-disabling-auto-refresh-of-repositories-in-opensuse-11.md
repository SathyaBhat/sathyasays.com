---
title: Disabling Auto-Refresh of Repositories in openSUSE 11
author: Sathya
type: post
date: 2008-08-18T15:27:31+00:00
url: /2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/
categories:
  - "Tips &amp; How-To's"
tags:
  - apt-get
  - DE
  - Debian
  - dl
  - download
  - downloads
  - DVD
  - IM
  - install
  - linux
  - open source
  - openSuSE
  - openSUSE 11
  - os
  - package manager
  - repo
  - repos
  - repositories
  - rm
  - RMS
  - software
  - subs
  - SUSE
  - synaptic
  - "tips-and-howto's"
  - tutorials
  - X
  - YaST

---
One of the heavily improved aspects of openSUSE 11 is the package manager and the way packages and repositories are handled. Although YaST [Yet Another Setup Tool, openSUSE&#8217;s system admin/configuration tool] is no longer the slow poke that it used to be, its still no match in terms of speed to Debian&#8217;s apt-get/Synaptic.
  
One of the more irritating part of YaST is that it auto-refreshes the repositories every time you launch the package management tool.ie, YaST downloads the info regarding all the packages that are available in the repo. Now if you&#8217;ve subscribed to multiple repos(most likely the case) or if you&#8217;re stuck on a slow connection, this can take the wind out of your sails, especially if you want to jsut install something from the DVD. So here&#8217;s a small step to disable auto-refresh of repos.
  
First head over to YaST, click on Software and then Software Repositories.

<p style="text-align: center;">
  <a href="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1.png"><img data-attachment-id="337" data-permalink="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/softrepo1/" data-orig-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1.png?fit=1280%2C800&ssl=1" data-orig-size="1280,800" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="softrepo1" data-image-description="" data-medium-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1.png?fit=300%2C187&ssl=1" data-large-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1.png?fit=740%2C463&ssl=1" class="alignnone size-thumbnail wp-image-337" title="softrepo1" src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1-150x150.png?resize=150%2C150" alt="" width="150" height="150" srcset="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/softrepo1.png?resize=150%2C150&ssl=1 150w, https://i1.wp.com/sathyasays.com/wp-content/uploads//home/sathya/public_html/wp-content/uploads/2008/08/softrepo1.png?zoom=2&resize=150%2C150&ssl=1 300w, https://i1.wp.com/sathyasays.com/wp-content/uploads//home/sathya/public_html/wp-content/uploads/2008/08/softrepo1.png?zoom=3&resize=150%2C150&ssl=1 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
</p>

Next,Select the repo, and ensure that Automatically refresh is disabled. That&#8217;s it!

<p style="text-align: center;">
  <a href="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh.png"><img data-attachment-id="336" data-permalink="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/refresh/" data-orig-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh.png?fit=895%2C600&ssl=1" data-orig-size="895,600" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="refresh" data-image-description="" data-medium-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh.png?fit=300%2C201&ssl=1" data-large-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh.png?fit=740%2C496&ssl=1" class="aligncenter size-thumbnail wp-image-336" title="refresh" src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh-150x150.png?resize=150%2C150" alt="" width="150" height="150" srcset="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/08/refresh.png?resize=150%2C150&ssl=1 150w, https://i0.wp.com/sathyasays.com/wp-content/uploads//home/sathya/public_html/wp-content/uploads/2008/08/refresh.png?zoom=2&resize=150%2C150&ssl=1 300w, https://i0.wp.com/sathyasays.com/wp-content/uploads//home/sathya/public_html/wp-content/uploads/2008/08/refresh.png?zoom=3&resize=150%2C150&ssl=1 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
</p>

The repos will no longer refresh automatically.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-334" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-334" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-334" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>