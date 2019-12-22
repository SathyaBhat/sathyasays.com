---
title: Making Dolphin the Default File Manager
author: Sathya
type: post
date: 2007-06-18T10:59:02+00:00
url: /2007/06/18/making-dolphin-the-default-file-manager/
categories:
  - News
tags:
  - Dolphin


---
Dolphin&#8217;s fast loading times and clean interface made me consider to have a second look at Dolphin. So here&#8217;s a way to make Dolphin the default file manager.

If you haven&#8217;t installed Dolphin yet, install it via apt-get or Adept. More info about that in my [previous post][1].

Then, Click on K Menu -> Run Command and type &#8216;kcontrol&#8217; (without the quotes, of course).

Then Click on KDE Components -> File Associations. Expand the inode section.</p> 

<p style="text-align:center;">
  <img src="http://sathyasays.wordpress.com/files/2007/06/dolphin-default.thumbnail.jpg" alt="dolphin-default.jpg" />
</p>

</a>Make Dolphin the first choice, by moving it above Konqueror in the precedence order. This will ensure that Dolphin gets the first priority for opening directories.

To make dolphin the default file manager for the virtual directories kde creates e.g. system:/ then again in the File Associations section of the control centre expand the inode section of Known Types. Under the system_directory mime type, add dolphin to the list of applications(If Dolphin entry is already present, remove it), however instead of choosing dolphin from the kmenu, type the following in to the text box at the top dolphin %u The virtual directories created by kde will then be opened by dolphin as default

Voila! Dolphin is now your default file manager!

 [1]: http://sathyasays.wordpress.com/2007/06/14/a-look-at-dolphin/