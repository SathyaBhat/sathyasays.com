---
title: Download your Spotify My Music songs as MP3
author: Sathya
type: post
date: 2015-12-29T17:22:56+00:00
url: /2015/12/29/spotify-dl-download-your-spotify-my-music-songs-as-mp3/
categories:
  - Programming
tags:
  - mp3
  - Spotify

---
I wanted a way to download my Spotify songs for offline listening. Ideally I'd subscribe to Spotify to make use of Offline feature, but they haven't officially launched here so that's out of the question.

A while back, I'd used <a href="https://github.com/frosas/spotify-to-mp3" target="_blank">spotify_to_mp3</a> which made use of Grooveshark to download, but Grooveshark shut down, leaving the script defunct. This gave me an idea to build something similar.

With this as the motivation, I built <a href="https://github.com/SathyaBhat/spotify-dl" target="_blank">Spotify-dl</a> to scratch an itch as well as to improve my Python skills. Since Spotify doesn't allow you to download songs directly, I followed the same approach as spotify\_to\_mp3 &#8211; which is

  * Login to your Spotify library
  * Fetch all your &#8220;My Music&#8221; tracks using <a href="https://developer.spotify.com/web-api/" target="_blank">Spotify Web API</a>
  * Parse the artist name & track name
  * Search for the artist name & track name against YouTube using <a href="https://developers.google.com/youtube/v3/?hl=en" target="_blank">their Data API</a> and grab their YouTube URLs
  * Pass the YouTube URLs to youtube-dl to download the songs
  * Profit!

It didn't take me long to build the glue script & python made it that much easier. The script is available on <a href="https://github.com/SathyaBhat/spotify-dl" target="_blank">my github</a>. Huge thanks to <a href="https://github.com/rhnvrm" target="_blank">Rohan</a> to contributing the youtube-dl integration part.

The <a href="https://github.com/SathyaBhat/spotify-dl#spotify-dl" target="_blank">readme has</a> the required documentation on how to get it up and running. Any feedback is welcome
