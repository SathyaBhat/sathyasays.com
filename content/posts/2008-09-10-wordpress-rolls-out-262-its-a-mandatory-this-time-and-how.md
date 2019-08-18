---
title: WordPress Rolls Out 2.6.2 – Its A Mandatory This Time – And How
author: Sathya
type: post
date: 2008-09-09T18:49:46+00:00
url: /2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/
categories:
  - News
tags:
  - Auto Upgrade
  - blog
  - DE
  - exploit
  - find
  - IM
  - open source
  - os
  - plugin
  - security
  - update
  - updating
  - upgrade
  - upgrading
  - user
  - WordPress
  - WordPress Automatic Upgrading
  - wordpress plugin
  - X
  - xp

---
The good people over at <a href="http://wordpress.org/" target="_blank">WordPress</a> released <a href="http://wordpress.org/development/2008/09/wordpress-262/" target="_blank">WordPress 2.6.2</a> today. And unlike the previous 2.6.1 release, this release is a mandatory release, to fix a loophole which occurs if your blog has registrations open.

From the horse&#8217;s mouth:

> If you allow open registration on your blog, you should definitely upgrade.  With open registration enabled, it is possible in WordPress versions 2.6.1 and earlier to craft a username such that it will allow resetting another user’s password to a randomly generated password.  The randomly generated password is not disclosed to the attacker, so this problem by itself is annoying but not a security exploit.  However, this attack coupled with a weakness in the random number seeding in mt_rand() could be used to predict the randomly generated password.

Certainly seems a very important reason to update to 2.6.2. And if you find the process of upgrading WordPress blog a pain, <a href="http://sathyasays.com/2008/09/10/how-toautomatically-backing-up-and-upgrading-your-wordpress-installation-and-wordpress-database/" target="_blank">here&#8217;s an effortless way of doing it</a>.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-369" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-369" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-369" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/09/10/wordpress-rolls-out-262-its-a-mandatory-this-time-and-how/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>