---
title: Updating to openSUSE 11.2
author: Sathyajith Bhat
type: post
date: 2009-11-15T08:34:36+00:00
url: /2009/11/15/updating-to-opensuse-11-2/
categories:
  - "Tips & How-To's"
tags:
  - linux
  - openSuSE


---
As mentioned openSUSE 11.2 is now available. If you're on previous versions of openSUSE you can do an inplace upgrade to 11.2 by using zypper.

openSUSE 11.0/openSUSE 11.1

Just change the repos to mention 11.2 instead of 11.0/11.1, as shown in the pic:



[<img class="aligncenter size-medium wp-image-796" title="opensuse repos" src="https://i.sathyabh.at/ss/2009/11/opensuse-repos-300x155.jpg" alt="opensuse repos"   srcset="https://i.sathyabh.at/ss/2009/11/opensuse-repos-300x155.jpg 300w, https://i.sathyabh.at/ss/2009/11/opensuse-repos.jpeg 1001w" sizes="(max-width: 300px) 100vw, 300px" />][1]

Once that's done, open the terminal, and switch to root

> su root

Then refresh the repos

> zypper ref

Finally, do the distribution upgrade

> zypper dup

**openSUSE 11.2 Milestone/RC versions:**

Be sure to disable Factory repo, else like me, you'll end up upgradingto 11.3!! Use the same steps as above, although you probably wouldn't have to change any repos, just disable the Factory and go ahead with the upgrade!

Here's a pic from my desktop after the upgrade:

<a id="aptureLink_48N5sHAeLS" style="margin: 0pt auto; padding: 0px 6px; text-align: center; display: block;" href="https://apture.s3.amazonaws.com/00000124f6f3ff797b1b4ed9007f000000000001.opensuse%20desky.jpeg"><img style="border: 0px none;" title="opensuse desky" src="https://apture.s3.amazonaws.com/00000124f6f3ff797b1b4ed9007f000000000001.opensuse%20desky.jpeg" alt="" width="622.96px" height="389.35px" /></a>

A word of caution: if you're on low bandwidth / low speed connection, it's better if you get the download the CD from your friend/LUG and do a fresh install.

And yes, if you have any third party repos, that might break so just be weary of that

 [1]: https://i.sathyabh.at/ss/2009/11/opensuse-repos.jpeg
