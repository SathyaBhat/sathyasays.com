---
title: '[How-To] Enable Auto-Mounting of External Drives In openSUSE 11'
author: Sathya
type: post
date: 2008-08-20T09:29:36+00:00
url: /2008/08/20/how-to-enable-auto-mounting-of-external-drives-in-opensuse-11/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - auto-mount
  - automount
  - cat
  - DE
  - Desktop
  - events
  - file
  - flash drive
  - free
  - HAL
  - hard drives
  - linux
  - LTS
  - media
  - mount
  - mounting
  - Novell
  - openSuSE
  - openSUSE 11
  - pen drive
  - PolicyKit
  - rm
  - root
  - script
  - subs
  - SUSE
  - switch
  - tar
  - terminal
  - usb
  - USB pen drive
  - X

---
Due to weird-ass PolicyKit rules, you may not be able to mount external drives &#8211; such as USB Hard drives, Pen drives, or other mass storage drives. while the drive gets recognised, on trying to mount you&#8217;ll end up with this error:

> org.freedesktop.hal.storage.mount-removable no <&#8211; (action, result)

This is because of a PolicyKit rule, which prevents external media from being mounted. To get around this, you&#8217;ll have to edit the policy. So first open the terminal. Switch to root by typing

>  `su root`

Next, open the PolicyKit config file corresponding to Storage. This file is located at

> `/usr/share/PolicyKit/policy/org.freedesktop.hal.storage.policy`

Open this file for editing, by typing
  
`kate /usr/share/PolicyKit/policy/org.freedesktop.hal.storage.policy`
  
Next, search for this section

> `<action id="org.freedesktop.hal.storage.mount-removable"><br />
<description>Mount file systems from external drives.</description><br />
<message>System policy prevents mounting external media</message><br />
<defaults><br />
<allow_inactive>no</allow_inactive><br />
<allow_active>yes</allow_active><br />
</defaults><br />
</action>`

And replace it with

> `<action id="org.freedesktop.hal.storage.mount-removable"><br />
<description>Mount file systems from external drives.</description><br />
<message>System policy prevents mounting external media</message><br />
<defaults><br />
<allow_inactive>yes</allow_inactive><br />
<allow_active>yes</allow_active><br />
</defaults><br />
</action>`

Save the file, and then restart the HAL subsystem by typing

> `rchal restart`

From now on, your external drives should be mounted with full access.