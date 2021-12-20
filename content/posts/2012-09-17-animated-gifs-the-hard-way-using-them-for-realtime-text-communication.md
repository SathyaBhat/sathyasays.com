---
title: 'Animated GIFs the Hard Way & Using Them For Realtime text communication'
author: Sathyajith Bhat
type: post
date: 2012-09-17T14:32:30+00:00
url: /2012/09/17/animated-gifs-the-hard-way-using-them-for-realtime-text-communication/
categories:
  - Programming
tags:
  - animated gif
  - gif

---
> When doing the new website for the Sublime Text 2.0 launch, instead of just screenshots, I wanted to have animations to demonstrate some of its features. Animated GIF files would have been a candidate, except for two issues: the 256 color limitation, which would have made the animations ugly, and the encoders I tried spat out huge files, at almost 1MB per-animation.
> 
> Instead, I wrote a small Python script that takes a collection of PNG frames as input, and emits a single packed PNG file as output, which contains all the differences between the frames, and some JSON meta-data specifying which bits of the packed PNG file correspond to each frame. JavaScript turns the PNG and JSON into an animation, using either the canvas element, or emulating it using overlaid div elements for older browsers.

via [Animated GIFs the Hard Way][1].

If you think that's crazy, check [gifsockets][2]

> This library demoes how to achieve realtime text communication using GIF images as transport. The idea is pretty simple.
> 
> We use Animated Gif images to stream data in real time to the browser. Since a gif image doesn't specify how many frames it has, once the browser opens it, it will keep waiting for new frames&#8230;

Amazingly, both work on IE6, according to the devs.

 [1]: https://www.sublimetext.com/~jps/animated_gifs_the_hard_way.html
 [2]: https://github.com/videlalvaro/gifsockets#gifsockets "gifsockets"
