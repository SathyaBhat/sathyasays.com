---
title: '[How-To]Send SMS from your Linux computer via your Mobile Phone'
author: Sathya
type: post
date: 2008-10-18T07:22:58+00:00
url: /2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/
categories:
  - Reviews
  - "Tips &amp; How-To's"
tags:
  - apt-get
  - Arch
  - beta
  - bluetooth
  - cat
  - DE
  - Desktop
  - Fedora
  - Fedora 10
  - GNOME
  - IM
  - install
  - linux
  - Mobile
  - move
  - New
  - open source
  - phone manager
  - phonemanager
  - Reviews
  - rm
  - Screen
  - sending sms
  - sending text message
  - show
  - sms
  - software
  - terminal
  - text message
  - "tips-and-howto's"
  - Ubuntu
  - ux
  - X
  - xp
  - yum

---
While exploring Fedora 10 Beta, I found this neat little app called [Phone Manager][1].

The about page of PhoneManager states

> Phone Manager is a program created to allow you to control aspects of your mobile phone from your GNOME 2 desktop..

<!--more-->


  
The about page does seem ambitious, somewhat like gammu/Wammu but so far only SMS(text messaging) send/receive feature has been implemented, its been done so very nicely!

PhoneManager sits unobtrusively in the Gnome panel, running in the background. When a you have received a new text/SMS message a popup appears on your screen showing the message and the number of the person who sent the message.

<p style="text-align: left;">
  For contacts and address book, PhoneManager integrates very nicely with Evolution. If you want to send an SMS or text message, just click on the PhoneManager icon (which is&#8230; a mobile phone!) and a screen as shown below pops up, where you can type the message. Enter the name of the receipient, and Phone Manager will suggest the names and number of the person. Simplicity at its best!
</p>

<a href="http://www.flickr.com/photos/sathyabhat/2951304044/" target="_blank"><img class="aligncenter" src="https://i2.wp.com/farm4.static.flickr.com/3201/2951304044_c904549ced_m.jpg?w=740" alt="Sending SMS using phone manager" data-recalc-dims="1" /></a>
  
Unfortunately PhoneManager doesn&#8217;t show the name of the person for a received message, even if the number exists in Contacts. Maybe this will be included in future releases.

<a href="http://www.flickr.com/photos/sathyabhat/2950451251/" target="_blank"><img class="aligncenter" src="https://i1.wp.com/farm4.static.flickr.com/3227/2950451251_81f941b573_m.jpg?w=740" alt="composing sms" data-recalc-dims="1" /></a>

PhoneManager can communicate with your mobile phone over Bluetooth, IrDA(infra red) or via any of the ports.

This is a highly recommended app!

Installation: Phone Manager comes with Fedora 10 [don&#8217;t know about previous versions].

To install in Fedora &#8211; open the terminal and type

> `yum -y install gnome-phone-manager`

or just search for PhoneManager in Add/Remove programs.

To install PhoneManager in Ubuntu open Terminal and type

> `apt-get install gnome-phone-manager`

or just search for PhoneManager in Add/Remove programs.

PhoneManager was originally developed by Edd Dumbill, and is currently maintained by Bastien Nocera.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-479" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-479" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-479" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/18/how-tosend-sms-from-your-linux-computer-via-your-mobile-phone/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://live.gnome.org/PhoneManager