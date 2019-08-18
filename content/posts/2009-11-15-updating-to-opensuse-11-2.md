---
title: Updating to openSUSE 11.2
author: Sathya
type: post
date: 2009-11-15T08:34:36+00:00
url: /2009/11/15/updating-to-opensuse-11-2/
categories:
  - "Tips &amp; How-To's"
tags:
  - DE
  - Desktop
  - download
  - install
  - linux
  - open source
  - openSuSE
  - openSUSE 11
  - openSUSE 11.0
  - opensuse 11.1
  - os
  - repo
  - repos
  - rm
  - root
  - show
  - SUSE
  - switch
  - terminal
  - "tips-and-howto's"
  - tutorials
  - update
  - updating
  - upgrade
  - upgrading
  - zypper

---
As mentioned openSUSE 11.2 is now available. If you&#8217;re on previous versions of openSUSE you can do an inplace upgrade to 11.2 by using zypper.

openSUSE 11.0/openSUSE 11.1

Just change the repos to mention 11.2 instead of 11.0/11.1, as shown in the pic:

<!--more-->

[<img data-attachment-id="796" data-permalink="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/opensuse-repos/" data-orig-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg?fit=1001%2C519&ssl=1" data-orig-size="1001,519" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="opensuse repos" data-image-description="" data-medium-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg?fit=300%2C155&ssl=1" data-large-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg?fit=740%2C384&ssl=1" class="aligncenter size-medium wp-image-796" title="opensuse repos" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos-300x155.jpg?resize=300%2C155" alt="opensuse repos" width="300" height="155" srcset="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg?resize=300%2C155&ssl=1 300w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg?w=1001&ssl=1 1001w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][1]

Once that&#8217;s done, open the terminal, and switch to root

> su root

Then refresh the repos

> zypper ref

Finally, do the distribution upgrade

> zypper dup

**openSUSE 11.2 Milestone/RC versions:**

Be sure to disable Factory repo, else like me, you&#8217;ll end up upgradingto 11.3!! Use the same steps as above, although you probably wouldn&#8217;t have to change any repos, just disable the Factory and go ahead with the upgrade!

Here&#8217;s a pic from my desktop after the upgrade:

<a id="aptureLink_48N5sHAeLS" style="margin: 0pt auto; padding: 0px 6px; text-align: center; display: block;" href="https://i1.wp.com/apture.s3.amazonaws.com/00000124f6f3ff797b1b4ed9007f000000000001.opensuse%20desky.jpeg"><img style="border: 0px none;" title="opensuse desky" src="https://i1.wp.com/apture.s3.amazonaws.com/00000124f6f3ff797b1b4ed9007f000000000001.opensuse%20desky.jpeg?resize=622%2C389" alt="" width="622 .96px" height="389 .35px" data-recalc-dims="1" /></a>

A word of caution: if you&#8217;re on low bandwidth / low speed connection, it&#8217;s better if you get the download the CD from your friend/LUG and do a fresh install.

And yes, if you have any third party repos, that might break so just be weary of that

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-795" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-795" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-795" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/11/15/updating-to-opensuse-11-2/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/11/opensuse-repos.jpeg