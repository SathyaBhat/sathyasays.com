---
title: 'Transcript of discussion between Matt Mullenweg and Chris Pearson – Summarizing #thesiswp'
author: Sathya
type: post
date: 2010-07-15T22:56:40+00:00
url: /2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/
topsy_short_url:
  - http://bit.ly/aq7SQ3
categories:
  - General
tags:
  - basics
  - blog
  - community
  - comparison
  - DE
  - dual
  - file
  - find
  - forums
  - free
  - fun
  - git
  - GPL
  - history
  - IM
  - images
  - iso
  - license
  - LTS
  - move
  - open source
  - os
  - PHP
  - quotes
  - read
  - rm
  - RMS
  - script
  - show
  - software
  - support
  - tar
  - theme
  - themes
  - Thesis
  - twitter
  - Unity
  - update
  - user
  - ux
  - web
  - WordPress
  - WP
  - write
  - X
  - xp

---
Couple of days ago, there was a huge debate (argument ?)  between Matt Mullenweg  &#8211; developer of WordPress and Chris Pearson &#8211; developer of Thesis premium theme over twitter which then extended to Mixergy.

Crux of the argument is the disagreement amognst the two over the licensing terms. Matt believes that Thesis should adopt [GPL][1]{#aptureLink_Q1kNtLltNY} which as Wikipedia states:

> The GPL is an example of a powerful [copyleft][2] license that requires derived works to be available under the same copyleft.

Chris, on the otherhand disagrees with this. The full transcript of their discussion is available on Mixergy, here are some quotes which I found interesting:

<!--more-->

> Andrew Warner:  Can you give us just a short version of what the issue is from your side?

> Matt Mullenweg: Sure. WordPress is built on the license of a GPL that has enabled hundreds of thousands of people to build amazing businesses off it. **All it really says is that you can do whatever you like but anything built on top of the GPL must be GPL itself. That’s the crux of it**.

> Matt: Thesis has stated publicly that they believe in a different interpretation of the GPL. The GPL doesn’t apply to them. That WordPress’ license doesn’t apply and they don’t need to follow it. That’s obviously harmful to the WordPress community and I would love them to join and be GPL.

> Matt: If you build a module for Drupal or a module for WordPress or a theme for WordPress or anything like that, the license says that you do have to follow the GPL. I think that it’s just a matter of choosing the platform. If you disagree with the GPL, just use a platform that doesn’t have the GPL.

> Andrew: Matt, when I had Chris on Mixergy you, in the comments, said that he can make one little change and he would be in compliance. What is that change? Then I’ll ask Chris how that would impact his business.
> 
> Matt: He just has to say it’s the GNU GPL. That’s it.
> 
> Andrew: If you took that, Chris, how would it impact your business?
> 
> Chris:  The most important one to me is simply my right as an individual to put out some creative work that is independent. [&#8230;]**WordPress did not empower me to write this software, I wrote all this stuff.** I thought about all this stuff. I thought about all the data structures inherent to hosting a webpage.

> Matt: Number two, the second point, is that your business would be hurt somehow if people could, as you say, take your code and sell it for cheaper or something like that. I think that undersells Thesis to an extent. I think that from what I’ve heard about people who like Thesis, it is much more than just a code and a theme it is the forums, the support, the community, and all the things around it that make it valuable. Second, there’s been every other premium theme developer and vendor in the world has already gone GPL and their businesses have been just fine.

> **Matt: You could even sell the theme itself. There is nothing in the GPL that says it has to be free.**

> Matt: Are you saying you want to be a test case for the GPL? You want us to sue you? I mean, that would break my heart. I’d rather you be part of the family.

> Chris: That’s unbelievable that you’re trying to dictate out on those terms after having such a flimsy license to begin with, that’s unenforceable.

> Chris: I’ve done great things with WordPress since 2006. I have been arguably one of the top three most important figures in the history of WordPress. You, Mark Jaquith, and myself, are the three people that I am talking about.
> 
> Matt: Well, first of all, I’m struck by your humbleness in that you think you are one of the top three people to deal with WordPress.

> Matt: Even in the premium theme market it looks like Thesis is under 10% of the premium theme market. There are just so many other alternatives out there that have really . . .
> 
> Chris: I think that is a pretty impressive share considering how many premium themes there are.
> 
> Matt: Well, less than 10% of the premium theme market, which is less than 5% of the total WordPress user base, less than 3% actually. You are looking at like 0.3% on the very, very high end of users, and that’s assuming that you have 50,000 to 100,000.

> Andrew: Matt, first of all, if Thesis is such a small part of the WordPress community as a whole and of even the premium theme community, can you just agree to disagree on this case and accept that he has a difference of opinion on this? Let him do business his way without confrontation?
> 
> Matt: I think the issue there is that, one, it’s a violation of the license and if we allow someone to violate the license so blatantly, so publicly, and he is not being quiet. He does tell other people that GPL doesn’t fly. That it doesn’t matter.

> Andrew: Matt, so if he doesn’t back away from his position right now. You’re not going to sue him. Right?
> 
> Matt: I really hope it doesn’t come to that.
> 
> Andrew: Does that mean that you are thinking of doing it?
> 
> Matt: Well, if in the WordPress community people started deciding that the GPL doesn’t apply that’s a very, very slippery slope. Not just for WordPress but for all of open source. Like you said, there hasn’t been a court case yet in the United States because every company, including big ones like Cisco, have backed down. If Chris wants to be the court case that proves the GPL, I am sure there are many people in the open source community that would love that opportunity.

> Chris: Is a license a law? I’m not familiar that it’s a law. I know it’s a license. I didn’t know it’s a law.
> 
> Matt: It’s law. It’s the same law that you feel protects your work and your license and the distribution or not distribution of Thesis. Yes. I think it is completely valid.

> Andrew: If you could be convinced that this is the right way for your business and the right away in general, would you change? Would you make this change?
> 
> **Chris: What? To go GPL?**
> 
> **Andrew: Yeah.**
> 
> **Chris: I’ve explained it so many times. No.**

I&#8217;m not a lawyer, neither do I know enough about WordPress, Thesis or the GPL to comment on this.

Do read the full transcript &#8211;  [Would WordPress Sue The Maker Of Thesis, A Leading WordPress Theme? – with Chris Pearson and Matt Mullenweg][3].

Update: Drew Blas has a post, analysing the GPL&#8217;d code in Thesis. His thoughts:

> The problem is then simply one of analysis: Does Thesis contain code from from WordPress? I wrote a quick script to find out. Here are the basics:
> 
>   * The script takes every line of WordPress source and puts it into an in-memory hash.
>   * Every line is lower cased and has all whitespace removed to prevent missing matches from simple indentation or capitalization changes
>   * This hash is then checked against every line in the Thesis source
>   * It checks only PHP files (for simplicity…avoiding images and such)
>   * It excludes lines less than 20 characters long: This could cause it to miss matches, but also helped to filter a lot of stuff like ‘**<?php**‘ lines
>   * It will fail to find code lines that have been modified
> 
> ### _The Results_
> 
> My conclusion is that Thesis does contain GPL licensed code from WordPress.  There were several examples that fit, so I’ve chosen the strongest one here that is sufficient to show that the code has been reused.  ONE OF the functions in question is:
> 
> <pre>wp_list_comments from wordpress/wp-includes/comment-template.php:1387</pre>
> 
> <pre>thesis_list_comments from thesis_17/lib/classes/comments.php:169</pre>
> 
> And you can see a comparison of the exact matching lines: <a href="http://gist.github.com/477051" target="_blank">http://gist.github.com/477051</a>

Read the full post over [at Drew&#8217;s blog][4].

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-888" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-888" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-888" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/07/16/transcript-of-discussion-between-matt-mullenweg-and-chris-pearson/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://en.wikipedia.org/wiki/GNU%20General%20Public%20License
 [2]: http://en.wikipedia.org/wiki//wiki/index.php?title=Copyleft "Copyleft"
 [3]: http://mixergy.com/chris-pearson-matt-mullenweg/
 [4]: http://drewblas.com/2010/07/15/an-analysis-of-gpled-code-in-thesis/