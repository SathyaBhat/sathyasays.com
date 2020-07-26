---
title: '[How-To] Fix Nautilus File Manager Title Bar(Window Decorator) disappearing when Emerald is enabled'
author: Sathya
type: post
date: 2008-09-21T18:36:25+00:00
url: /2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/
categories:
  - "Tips & How-To's"
tags:
  - linux
  - nautilus

---
Most of the how-to's and fixes posted here, are generally my experiences and I post them on how I went about fixing it. This particular how-to was mentioned to me by my very good friend, Bharath, who had this annoying problem of the title bars of every window crashing and disappearing when Emerald is chosen as the decorator.

Generally, I'd recommend running `gtk-window-decorator --replace` or `metacity --replace` in terminal - that generally does reinitialize the window decorators. However for Bharath, this particular solution didn't help and he kept facing the same problem

<!--more-->

Despite typing the above, the title bars would still keep crashing. After some problem he was able to fix it. This is how he went about it.

 

  1. Open Gconf-editor
  2. Head to Applications -> Nautilus -> Preferences
  3. Modify key "navigation\_windows\_saved_geometry" to a resolution, that is lesser than the current screen resolution.

<div>
  Do note that you should ideally do this with none of the Nautilus windows open. Save Gconf editor, and launch Nautilus, the title bars should be back now.
</div>

<div>
  Thanks for the tip, Bharath, I'm sure many people will find this tip useful.
</div>
