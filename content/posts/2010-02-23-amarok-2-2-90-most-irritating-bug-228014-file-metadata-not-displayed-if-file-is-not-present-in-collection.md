---
title: 'Amarok 2.2.90 Most Irritating Bug #228014: File metadata not displayed If File Is Not Present In Collection'
author: Sathyajith Bhat
type: post
date: 2010-02-22T23:04:44+00:00
url: /2010/02/23/amarok-2-2-90-most-irritating-bug-228014-file-metadata-not-displayed-if-file-is-not-present-in-collection/

categories:
  - General
tags:
  - Amarok
  - applications
  - linux


---
Well it's no secret that I'm a music fan and love to keep my music organized, and neatly tagged. ( Well, if you didn't - now you do ). I'd posted quite sometime ago on how to keep your music [well tagged and organized][1], so there's pretty much no way that my files wouldn't be tagged.

Of course, there exceptions here and there but majority are tagged. So I was rather surpised today when Amarok , during playback wasn't showing any metadata. To verify - I installed id3v2, a CLI tool to view/edit ID3 tags for mp3 files using zypper and - guess what- it showed the meta data correctly.
  


<p style="text-align: center;">
  <figure style="width: 622px" class="wp-caption aligncenter"><a href="https://imagebin.ca/img/Vd4Ku-B.jpg"><img class=" " title="ID3 tag - gone!" src="https://imagebin.ca/img/Vd4Ku-B.jpg" alt="ID3 tag - gone!"   /></a><figcaption class="wp-caption-text">ID3 tag - gone!</figcaption></figure> 
  
  <p>
    I tried this for few more songs so that I can reproduce this, and confident of that, fired up the bug report tool and filed in a <a id="aptureLink_AJTpe7PkTC" href="https://bugs.kde.org/show_bug.cgi?id=228014">bug for the same</a>. In few hours, I got an email notification about change in status of the bug. Here's what Myriam asked me:
  </p>
  
  <blockquote>
    <p>
      Are those tracks in the collection? You might want to try a full collection<br /> rescan and restart Amarok to see if it changes.
    </p>
  </blockquote>
  
  <p>
    On checking, - the tracks had mysteriously disappeared from my collection. I rescanned the collection, still it showed nothing. Quit Amarok, restarted, and lo, it was there :|<br /> So the bug - if the tracks aren't in collection, then the meta data for them is not read / skipped. Why ? I don't know. Perhaps the developersthought,
  </p>
  
  <blockquote>
    <p>
      hey the track isn't in collection, so lets not parse the meta data and we'll skip gathering the stats.
    </p>
  </blockquote>
  
  <p>
    .
  </p>
  
  <p>
    Note: This is what *I* think, I'm nowhere implying that this is by design of Amarok.
  </p>
  
  <p>
    It'll be interesting to see how the bug gets tracked and what happens to it. Will keep updating it.
  </p>
  
  <p>
    (PS: If you're wondering why its irritating, well, without the metadata the last.fm scrobbler won't pick up the song and scrobble the play. Maybe you think its stupid, but *meh*).
  </p>

 [1]: https://sathyabh.at/2008/07/27/how-organise-and-tag-music-mp3-files-automatically-using-musicbrainz-picard-tagger/
