---
title: Some Really Cool And Must Have Amarok Scripts
author: Sathya
type: post
date: 2008-08-02T19:26:34+00:00
url: /2008/08/03/some-really-cool-and-must-have-amarok-scripts/
categories:
  - "Tips &amp; How-To's"
tags:
  - Amarok
  - Arch
  - audio player
  - autotorrent
  - AWN
  - bestof
  - cover
  - Cover fetcher
  - cover print
  - DE
  - delete
  - Desktop
  - download
  - downloads
  - file
  - Flex
  - IM
  - images
  - inkscape
  - internet
  - LastSync
  - linux
  - media
  - menu
  - Mplayer
  - music
  - net
  - os
  - personal
  - read
  - replaygain
  - review
  - rm
  - RMS
  - script
  - scripts
  - software
  - SQLite
  - support
  - sync
  - tar
  - torrents
  - transkode
  - ux
  - videos
  - web
  - weekalarm
  - windows
  - write
  - X
  - xp

---
Amarok is probably amongst the best audio player and jukebox software, bar none. This feature rich software is  also very flexible and extensible. By making use of third party scripts (and writing your own, if you know, say Python or Ruby) you can enrich your experience your Amarok experience. Here’s a list of some must have Amarok scripts

  * **weekalarm** 

weekalarm is one heck of a alarm script – you can set multiple alarms for the day, different times for different days, support for snooze and nap, make use of fading, and even use a separate playlist for your alarm tunes. Can’t imagine waking up without this one!

<!--more-->

Download weekalarm from <a href="http://kde-apps.org/content/show.php/weekalarm?content=23160" target="_blank">here</a>.

  * **Replaygain**

Replaygain is an Amarok script which normalizes your playlist and ensures that all of your songs play at the same volume. The normalization process is done using the replaygain method and hence the name of the script. You’ll have to ensure that the replaygain is calculated first – by scanning all your music files for every track/album. Do note that this might take a while, so its best if you schedule this scanning for say night when you’re off to sleep.

Get <a href="http://kde-apps.org/content/show.php/ReplayGain?content=26073" target="_blank">Replaygain</a>.

  * **transKode / Audio Format Converter**

transKode is script which allows for re-encoding/transcoding of your media files to other formats. This script adds a “transKode” entry to Amarok’s right click context menu and you can choose the required profile and your media file will be converted.

Another similar script is Audio Format Converter but personally I prefer transKode

Download <a href="http://kde-apps.org/content/show.php/transKode?content=27512" target="_blank">transKode</a> / <a href="http://kde-apps.org/content/show.php/Audio+Format+Converter?content=23653" target="_blank">Audio Format Converter</a>.

  * **Autoplay Videos**

Autoplay videos automatically launches a video player of your choice(mplayer by default) whenever a video file is detected. Neat if you want Amarok to maintain your entire media collection – be it videos or music.

Download <a href="http://kde-apps.org/content/show.php/Autoplay+Videos?content=72793" target="_blank">Autoplay Videos</a>

  * **Amarok Desktop Script / AWN Amarok Minisec**

Amarok Desktop Script displays the Cover art on you desktop.

AWN Amarok Minisec displays the cover art on the dock instead of default Amarok icon.

Download <a href="http://kde-apps.org/content/show.php/amaroK+Desktop+Script?content=20293" target="_blank">Amarok Desktop Script</a> / <a href="http://kde-apps.org/content/show.php/awn-amarok-minsec?content=57893" target="_blank">AWN Amarok Minisec</a>

  * **Amarok Cover Fetcher**

This script allows fetching album cover art for the currently playing track from discogs.com by clicking onto any track in the playlist and selecting: &#8220;Fetch Covers&#8221; -> &#8220;For Currently Playing Track&#8221;
  
Already existing local album art (image files from the currently playing track&#8217;s folder) as well as relevant album art from Last.fm and Discogs.com can then be browsed / saved / deleted.

Download [Cover Fetcher][1]

  * **CoverPrint**

CoverPrint creates CD cover images of the Amarok playlist, ready for printing. The templates are inkscape files, which can be easily modified to your own taste.

<a href="http://kde-apps.org/content/show.php/CoverPrint?content=36670" target="_blank">Download CoverPrint</a>

  * **AutoTorrent**

This script adds a “Download this album” option to Amarok’s right click context menu, and when clicked, searches through Mininova and TorrentSpy for the album and starts the torrent client automatically.

Download [AutoTorrent][2]

  * **GoogLyrics**

GoogLyrics is based on EvilLyrics which rip lyrics off known website and gets a high success rate in extraction of lyrics even for some obscure songs. It searches for lyrics from sites like <a href="http://www.lyricsmania.com" target="_blank">LyricsMania</a>.

Download <a href="http://kde-apps.org/content/show.php/GoogLyrics?content=73850" target="_blank">GoogLyrics</a>

  * **LyricsID3**

This script fetches the lyrics not from the Internet, but uses ID3 tag of mp3 files to fetch/store the same. So if there are lyrics stored in file and this script is running, Amarok will display the lyrics.
  
ID3v2 allows to store multiple lyrics in one file. This script also supports read/write of lyrics to Vorbis and FLAC files. This script also supports saving and deletion of lyrics.

<a href="http://kde-apps.org/content/show.php/Lyrics+ID3?content=49274" target="_blank">Download LyricsID3</a>

  * **LastSync**

LastSync is a ruby script which downloads your last.fm statistics like playcount of your music files and saves it to your Amarok database. This is particular useful if you scrobble from many sources (Linux, Windows, iPod &#8230;) but want to have a accurate Amarok statistic. Currently works only on SQLite collection database.

<a href="http://kde-apps.org/content/show.php/Last+Sync?content=65784" target="_blank">Download LastSync</a>

  * **collection2HTML**

This neat little script exports your entire collection to a HTML file, ordered by Artist and Album

Download <a href="http://kde-apps.org/content/show.php/collection2html?content=61476" target="_blank">collection2HTML</a>

Hope this list was useful to you all. Do you guys use any script that I haven&#8217;t mentioned? Do drop a comment and letme know

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-333" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-333" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-333" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/08/03/some-really-cool-and-must-have-amarok-scripts/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://kde-apps.org/content/show.php/Cover+Fetcher+(for+AmaroK)?content=83909
 [2]: http://kde-apps.org/content/show.php/Autotorrent?content=53391