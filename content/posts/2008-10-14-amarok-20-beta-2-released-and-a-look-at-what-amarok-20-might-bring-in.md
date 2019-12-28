---
title: Amarok 2.0 Beta 2 Released And a look at what Amarok 2.0 might bring in
author: Sathya
type: post
date: 2008-10-13T19:46:33+00:00
url: /2008/10/14/amarok-20-beta-2-released-and-a-look-at-what-amarok-20-might-bring-in/
categories:
  - News
  - Previews
tags:
  - AIR
  - Amarok
  - Amarok 2
  - amarok2
  - audio player
  - beta
  - blog
  - chm
  - comparison
  - DE
  - file
  - IM
  - install
  - iso
  - KDE
  - KDE4
  - music
  - MusicBrainz
  - MySQL
  - nepomuk
  - New
  - Opera
  - os
  - performance
  - plasmoid
  - plasmoids
  - PostgreSQL
  - preview
  - replaygain
  - repo
  - review
  - rm
  - RMS
  - script
  - scripts
  - show
  - SQLite
  - strigi
  - subs
  - support
  - switch
  - usb
  - user
  - X
  - xp

---
Couple of days ago, the second beta to the second version of the immensely popular and fantastic audio player Amarok was <a href="https://amarok.kde.org/blog/archives/807-Amarok-2-Beta-2-released.html" target="_blank">released</a> by the Amarok team.

The second beta brings in some drastic changes, the main one being SQLite no longer being the default backend, and PostgreSQL support being dropped, in favour of a single backend, that being MySQL-Embedded platform. Other notable changes include improved scripting support, the return of lyric fetching and incremental scanner support.

<!--more-->

Amarok 2.0 Beta will also not be on the same level, feature-wise, with Amarok 1.4 as the developers are rewriting most of Amarok codebase meaning that most of Amarok 1.4 scripts will not be compatible with Amarok 2.0 ones (and the list of Amarok 1.4 scripts is pretty huge, you might want to have a look at <a href="sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/" target="_blank">Some of the coolest Amarok scripts</a>)

<a href="https://1.bp.blogspot.com/_vlB73cxVKVI/SOr9Xk4OGJI/AAAAAAAAAF8/9eNUkLdG5w4/s1600-h/applet3.png" target="_blank"><img src="https://1.bp.blogspot.com/_vlB73cxVKVI/SOr9Xk4OGJI/AAAAAAAAAF8/9eNUkLdG5w4/s400/applet3.png" /></a> 

(Pic taken from Amarok blog)

In subsequent blog posts [Mark Kretschmann][1] has mentioned, which features Amarok 2.0 feature, such as

  * Visualizations
  * Equalizer
  * USB mass storage devices support
  * Crossfading
  * Stop after this track
  * Queue feature
  * Dynamic Collection
  * Cue file support
  * Collection statistics
  * Playlist sorting
  * Showing new tracks in collection
  * Labels
  * ReplayGain

And the following features have been dropped in Amarok 2.0

  * <a href="https://amarok.kde.org/blog/archives/502-Playlist-mockup,-part-deux.html" target="_blank">Old style</a> playlist, "<a href="https://amarok.kde.org/blog/archives/810-The-Old-style-Playlist-Is-Dead,-Long-Live-The-Old-style-Playlist.html" target="_blank">Excel Look</a>"
  * Support for Amarok 1 scripts
  * Multiple databases (SQLite and PostgreSQL)
  * Player Window 
  * MusicBrainz 

While Player window going missing might seem like a huge WTF, the developers plan to bring it in as a <a href="https://sathyasays.com/tag/plasmoid" target="_blank">Plasmoid</a>.

[Jeff Mitchell][2] explains in <a href="https://amarok.kde.org/blog/archives/812-MySQL-in-Amarok-2-The-Reality.html" target="_blank">his blog post</a> as to why SQLite and PostgreSQL was dropped:

> Since I mentioned Nepomuk, it&#8217;s time to discuss another common question/demand/complaint: _KDE has this nice Strigi-Nepomuk thing going on&#8230;why aren&#8217;t we using it for scanning music and storing information?_ There are a couple main reasons. The first is that Strigi and Nepomuk are optional, not required. We can&#8217;t rely on the user installing them, and even if they are installed, we can&#8217;t rely on the user to configure them properly.
> 
> The second reason is speed: Amarok&#8217;s custom collection scanner is extremely fast and pulls out specific pieces of information with TagLib. Strigi is, by comparison, very slow.
> 
> Now we had to choose the type. At first, SQLite seemed like a good choice, it&#8217;s decently fast. It&#8217;s pretty stable.The first problem is performance, Although for people with small collections it performs fairly well, people with large collections that switched to the MySQL or PostgreSQL backends in A1 would report enormous speed gains when operations performing complex or many queries were performed.
> 
> However, just as we can&#8217;t rely on the user to set up Strigi/Nepomuk correctly, we can&#8217;t rely on them to get their tables set up in MySQL or PostgreSQL. So we needed the database to be embeddable, PostgreSQL, does not have any such thing, leaving us with MySQL.

Amarok 2.0 is shaping up to be an impressive and total overhaul of Amarok, will have a preview of Amarok 2.0 soon.

 [1]: https://amarok.kde.org/blog/authors/2-Mark-Kretschmann
 [2]: https://amarok.kde.org/blog/authors/14-Jeff-Mitchell
