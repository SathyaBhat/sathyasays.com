---
title: Trouble Remembering Passwords? Have a Revelation!
author: Sathya
type: post
date: 2007-12-09T20:00:41+00:00
url: /2007/12/10/trouble-remembering-passwords-have-a-revelation/
categories:
  - General
tags:
  - Apple
  - applications
  - apps
  - apt-get
  - Arch
  - browser
  - cat
  - DE
  - Desktop
  - desktop environment
  - desktop environments
  - dl
  - Fedora
  - file
  - gconf
  - GNOME
  - Home
  - IM
  - install
  - KDE
  - linux
  - login
  - Master
  - menu
  - Nautilus
  - net
  - open source
  - os
  - rm
  - root
  - Screen
  - security
  - shell
  - smb
  - software
  - sudo
  - support
  - tar
  - terminal
  - theme
  - Ubuntu
  - update
  - user
  - warning
  - web
  - X
  - xp
  - yum

---
Consider this: You&#8217;re sitting infront of your desktop, with the login screen infront of you. However, you can&#8217;t seem to recall the username/password combo. Frustrating isn&#8217;t it? Here&#8217;s an application which is a fit solution for the problem: Revelation.

Revelation is a password manager application, mainly designed for the Gnome desktop. (This doesn’t mean however that you won’t be able to used in other desktop environments such as KDE or Xfce, it’s just that you won’t be able to enjoy the full features package.) It stores all your sensitive data in an encrypted XML file, protected by AES encryption which you can access using a master password. Basically, if you decide to use this program, the master password will be the single one you’ll even have to remember from now on, for the rest of your (online) life.

### Features:

<!--more-->

  * Secure: passwords are stored in an AES-encrypted data file with cipher block chaining.
  * User-friendly: tries to be intuitive, convenient, and HIG-compliant.Has support for drag-and-drop and unlimited undo/redo, and can both generate and test passwords for you. You can also open accounts in external applications, such as a browser, FTP-client, or ssh terminal, with a single click.
  * Organized: has several account types, including website, credit card, shell, ftp, and more, which can be stored in a tree-like structure using folders. Accounts can be found quickly and easily with the built-in search.
  * Panel applet: has a GNOME panel applet which lets you easily browse or search your accounts without having to start Revelation.
  * Remote access: gnome-vfs is used for loading and saving files, so you can access your accounts via ssh, webdav, smb, http, ftp, and much more.
  * Import/export: can handle datafiles from Password Safe 1.x and 2.x, GPass 0.4.x and 0.5.x, Figaro’s Password Manager, MyPasswordSafe, Password Gorilla, .netrc, XML, and plain text.
  * GNOME-integrated: tries to integrate tightly with GNOME &#8211; uses the GNOME icon theme, gnome-vfs, session manager, and gconf, and registers menu item and file mimetype for Nautilus.
### Installation & Usage

**Ubuntu:**  `$ sudo apt-get install revelation`
  
**Fedora:**  `$ sudo yum install revelation`
  
Once installed, you can run it from the Accessories menu. The first thing you need to do is create the file that will store your data so press the Save button and choose a name for it (.rev for example so it will also be hidden, inside your home directory). You will then be asked for the master password which will protect your sensitive data so choose it wisely.

After that, start creating the entries or import the data file if you have been using a different password manager.

**Unfortunately, there’s a security warning you should be aware of before using Revelation:**

> When Revelation is running and has opened a data file, both the file contents and the file password are stored in memory as plaintext. The root user or other programs on your computer may be able to access this data. This is unfortunate, but it is hard to avoid, and a problem Revelation shares with most other applications of this type.
> 
> Please only use Revelation on your own computers, and take normal security precautions such as keeping your software updated and using a firewall.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/12/10/trouble-remembering-passwords-have-a-revelation/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-192" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/12/10/trouble-remembering-passwords-have-a-revelation/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-192" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/12/10/trouble-remembering-passwords-have-a-revelation/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-192" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/12/10/trouble-remembering-passwords-have-a-revelation/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/12/10/trouble-remembering-passwords-have-a-revelation/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>