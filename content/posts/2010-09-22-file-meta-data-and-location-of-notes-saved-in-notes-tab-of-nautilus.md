---
title: File meta data and location of notes saved in notes tab of Nautilus
author: Sathya
type: post
date: 2010-09-22T01:49:11+00:00
url: /2010/09/22/file-meta-data-and-location-of-notes-saved-in-notes-tab-of-nautilus/
topsy_short_url:
  - https://bit.ly/cVWzgN
categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux
  - Nautilus
  - tutorials

---
I spend quite a lot of time on Super User( [my][1] [rep][2]is a testament to that I guess ;) ) - both on the site as well as the mindblowingly awesome [chat][3] (if you haven't been here, you \*must\* drop by).

Today a user dropped by and asked a very nice question - [which went like][4] -

> I have some files that have some text in the notes fields(the tab where you put notes in the properties dialog box)&#8230; so can I output those texts with using the ls command.

<!--more-->

Now me being a [KDE][5] user I had noticed this but never paid much attention. This piqued my interest, and I fired a quick search on "[notes in gnome file properties][6]" - this returned few results, all of them corroborating that the meta data is stored in an XML file in ~/.nautilus/metafiles. So I told him about the location. He replies stating that the path does not exist and ~/.nautilus is empty. Now that prompted me to get off my Windows partition and boot into Gnome ( probably the second time that I've booted into it after installing Ubuntu - as I said above I'm more of a KDE guy :-) ) and find out for myself where this is.

First thing I did run a system wide find for metafiles folder:

`find / -iname metafiles`

That didn't return anything, so I went back to the big G and searched deeper, to find [this launchpad answer][7]{#aptureLink_T6LEzmUe3M} :

> This is handled in gvfs now, and the information is stored in ~/.local/shared/gvfs-metadata

And indeed, it was

<img class="aligncenter" title="Notes" src="https://i.imgur.com/CWYMH.png" alt=""   />

Unfortunately, given the data stored against it, I don't think it would be possible to parse out the Notes data (The note I had saved was "where will this note be saved?").

Just another thing you learn every day :)

 [1]: https://superuser.com/users/4377/sathya
 [2]: https://superuser.com/users/flair/4377.png
 [3]: https://chat.superuser.com
 [4]: https://chat.superuser.com/transcript/message/11632
 [5]: https://sathyasays.com/tag/kde/
 [6]: https://www.google.com/search?q=notes+in+gnome+file+properties&hl=en
 [7]: https://answers.launchpad.net/ubuntu/+source/gvfs/+question/93098
