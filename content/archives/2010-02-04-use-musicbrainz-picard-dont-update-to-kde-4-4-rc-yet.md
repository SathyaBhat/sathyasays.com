---
title: Use MusicBrainz Picard ? Don’t update to KDE 4.4 RC (yet)
author: Sathyajith Bhat
type: post
date: 2010-02-04T01:43:33+00:00
url: /2010/02/04/use-musicbrainz-picard-dont-update-to-kde-4-4-rc-yet/

categories:
  - News
tags:
  - linux
  - applications


---
I love MusicBrainz Picard. It keeps my [music collection organized, tags and renames them][1], and heck even fetches the cover art for (almost) all songs. Picard is just brilliant.

And the icing on the cake - its FOSS & cross platform. And it was working fine - till couple of days ago.
  


Eager to try out the RC of the upcoming 4.4 release of KDE, I upgraded it. Later on I got a bunch of music files from Ankit, and I set to tag 'em correctly. Double clicked Picard. Bouncy icon starts, and then - nothing. Uh-oh. Rinse, repeat, no change. Wondering what could've happened, I launched Konsole and passed the command And - boom.

> sathya@shaman:~> picard
  
> Traceback (most recent call last):
  
> File "/usr/bin/picard", line 2, in
  
> from picard.tagger import main; main(&#8216;/usr/share/locale', True)
  
> File "/usr/lib/python2.6/site-packages/picard/tagger.py", line 21, in
  
> from PyQt4 import QtGui, QtCore
  
> RuntimeError: the sip module implements API v6.0 but the PyQt4.QtGui module requires API v7.0

Seems the upgrade in Qt has resulted in MusicBrainz Picard being broken :(. As of now there seems to be no solution - perhaps wait and watch till someone notices and fixes it ? Or dive into code and try to fix it myself ( mmm enticing). Anybody reading this has a solution ? Do drop a comment

 [1]: https://sathyabh.at/2008/07/27/how-organise-and-tag-music-mp3-files-automatically-using-musicbrainz-picard-tagger/
