---
title: Download your Spotify My Music songs as MP3
author: Sathya
type: post
date: 2015-12-29T17:22:56+00:00
url: /2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/
categories:
  - Programming
tags:
  - download
  - mp3
  - Spotify

---
I wanted a way to download my Spotify songs for offline listening. Ideally I&#8217;d subscribe to Spotify to make use of Offline feature, but they haven&#8217;t officially launched here so that&#8217;s out of the question.

A while back, I&#8217;d used <a href="https://github.com/frosas/spotify-to-mp3" target="_blank">spotify_to_mp3</a> which made use of Grooveshark to download, but Grooveshark shut down, leaving the script defunct. This gave me an idea to build something similar.

With this as the motivation, I built <a href="https://github.com/SathyaBhat/spotify-dl" target="_blank">Spotify-dl</a> to scratch an itch as well as to improve my Python skills. Since Spotify doesn&#8217;t allow you to download songs directly, I followed the same approach as spotify\_to\_mp3 &#8211; which is

  * Login to your Spotify library
  * Fetch all your &#8220;My Music&#8221; tracks using <a href="https://developer.spotify.com/web-api/" target="_blank">Spotify Web API</a>
  * Parse the artist name & track name
  * Search for the artist name & track name against YouTube using <a href="https://developers.google.com/youtube/v3/?hl=en" target="_blank">their Data API</a> and grab their YouTube URLs
  * Pass the YouTube URLs to youtube-dl to download the songs
  * Profit!

It didn&#8217;t take me long to build the glue script & python made it that much easier. The script is available on <a href="https://github.com/SathyaBhat/spotify-dl" target="_blank">my github</a>. Huge thanks to <a href="https://github.com/rhnvrm" target="_blank">Rohan</a> to contributing the youtube-dl integration part.

The <a href="https://github.com/SathyaBhat/spotify-dl#spotify-dl" target="_blank">readme has</a> the required documentation on how to get it up and running. Any feedback is welcome

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1308" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1308" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1308" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>