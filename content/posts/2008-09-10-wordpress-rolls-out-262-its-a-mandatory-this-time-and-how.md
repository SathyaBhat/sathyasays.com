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