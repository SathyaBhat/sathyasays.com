---
title: December 7th Fedora update breaks PackageKit, gives failed to get a TID Error
author: Sathya
type: post
date: 2008-12-09T03:33:39+00:00
url: /2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/
categories:
  - "Tips &amp; How-To's"
tags:
  - boot
  - Cambridge
  - DE
  - Desktop
  - events
  - Failed to get TID error
  - Fedora
  - Fedora 10
  - file
  - free
  - GNOME
  - Google
  - hassles
  - IM
  - install
  - KDE
  - media
  - package manager
  - PackageKit
  - PolicyKit
  - root
  - security
  - tar
  - TID error
  - update
  - user
  - X
  - xp

---
Well I&#8217;d just shifted to Fedora couple of days ago, and yesterday I&#8217;d applied the latest updates. Later on I thought I&#8217;ll explore the system a bit and decided to use the package manager KPackageKit (I&#8217;m on KDE). KPackageKit though, was not returning any packages. I thought I might have screwed up KPackgeKit, so I installed the Gnome version of PackageKit. Only then I realized, that something was wrong.

<!--more-->

On querying for a package I got this error:

> failed to get a TID: A security policy in place prevents this sender from sending this message to this recipient, see message bus configuration file (rejected message had interface &#8220;org.freedesktop.PackageKit.Transaction&#8221; member &#8220;GetUpdates&#8221; error name &#8220;(unset)&#8221; destination &#8220;org.freedesktop.PackageKit&#8221;)

Googled for this error, and immediately came to know lot more people were facing the same problem, and its because of a dbus security update: This update modifies the config file to reject all requests coming from packagekit, and hence KPackageKit wasn&#8217;t returning any packages. Atleast Gnome-PackageKit returned the error message, if I hadn&#8217;t tried that(gnome-packagekit) I wouldn&#8217;t know what the problem was!
  
Anyways a temporary fix is mentioned [here][1]. If it isn&#8217;t too clear, edit `/etc/dbus-1/system.d/org.freedesktop.PackageKit.conf` to include

> `<allow send_interface="org.freedesktop.PackageKit.Transaction"/><br />
` 

in the file after `<policy context="default">`

ie, the file should look like this now

> `<!DOCTYPE busconfig PUBLIC<br />
"-//freedesktop//DTD D-BUS Bus Configuration 1.0//EN"<br />
"http://www.freedesktop.org/standards/dbus/1.0/busconfig.dtd"><br />
<busconfig>`
> 
> <!&#8211; This configuration file specifies the required security policies
  
> for the PackageKit to work. &#8211;>
> 
> <!&#8211; Only user root can own the PackageKit service &#8211;>
  
> <policy user=&#8221;root&#8221;>
  
> <allow own=&#8221;org.freedesktop.PackageKit&#8221;/>
  
> </policy>
> 
> <!&#8211; Allow anyone to call into the service &#8211; we&#8217;ll reject callers using PolicyKit &#8211;>
  
> <policy context=&#8221;default&#8221;>
  
> <allow send_interface=&#8221;org.freedesktop.PackageKit&#8221;/>
  
> <allow send_interface=&#8221;org.freedesktop.PackageKit.Transaction&#8221;/>
  
> </policy>
  
> </busconfig>

Hope that helps.

**EDIT: As Janus & MH mention, do reboot the system or restart the dbus service for changes to take effect.**

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-596" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-596" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-596" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/12/09/december-7th-fedora-update-breaks-packagekit-gives-failed-to-get-a-tid-error/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://bugs.freedesktop.org/show_bug.cgi?id=18931