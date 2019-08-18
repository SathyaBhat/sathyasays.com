---
title: Enabling And Disabling Root Account in Debian/Ubuntu
author: Sathya
type: post
date: 2008-05-27T04:30:35+00:00
url: /2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/
categories:
  - "Tips &amp; How-To's"
tags:
  - cat
  - DE
  - Debian
  - distro
  - distros
  - dl
  - file
  - IM
  - laptop
  - linux
  - login
  - New
  - open source
  - os
  - read
  - root
  - security
  - sudo
  - tar
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - UNIX
  - update
  - X

---
<span style="text-decoration: line-through;">Debian and other debian-based distros like</span> Ubuntu <span style="text-decoration: line-through;">have</span>, by default, has the root account disabled as a security measure.(thanks to Subbu and PICCORO for the clarification)

To re-enable the root account, just open the command prompt, and type

> `sudo passwd root`

You&#8217;ll get the following set of messages:

> `sathya@sathya-laptop:~$ sudo passwd root<br />
Enter new UNIX password:<br />
Retype new UNIX password:<br />
passwd: password updated successfully<br />
sathya@sathya-laptop:~$`

To disable root access, just type

> `sudo passwd -l root`

If you&#8217;re weary of using the command line(you shoudn&#8217;t ;) ) then there&#8217;s another way:
  
Just head over to System > Administration > Login Window > Security > and check mark the box beside Allow local system administrator login.

DISCLAIMER: Christof Baumann mentions in [**this**][1] post as to why you shouldn&#8217;t fiddle with the root account:

> Be aware of locking the root account if you once activated it. I activated the root account and skipped the %admin ALL=(ALL) ALL line int /etc/sudoers file because i thought i wouldn’t need it anymore. Then i disabled the root account without thinking and now had no chance to start programs with root rights. Luckily i could restore it using a knoppix live cd. Be aware of changing settings concerning the root account.

Also, read [**this**][2] article in Ubuntu Wiki as to why sudo is preferred over standard root account.

PS: Just incase you guys are wondering why I&#8217;ve posted this basic info so late, well I&#8217;m just getting the hang of Ubuntu.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-308" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-308" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-308" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.ducea.com/2006/06/21/ubuntu-how-to-enable-the-root-account/
 [2]: https://help.ubuntu.com/community/RootSudo