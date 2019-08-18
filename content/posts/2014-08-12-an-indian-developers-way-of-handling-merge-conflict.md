---
title: An Indian developer’s way of handling merge conflict
author: Sathya
type: post
date: 2014-08-12T06:15:25+00:00
url: /2014/08/12/an-indian-developers-way-of-handling-merge-conflict/
evolve_full_width:
  - no
evolve_slider_type:
  - no
categories:
  - Programming
tags:
  - stupidity
  - WTF

---
So this happened just now with a colleague. He&#8217;s been working for few months now.

My way of handling merge conflict:

  1. Open WinMerge to diff
  2. See the conflicting part
  3. Correct the conflicting part by copying the changes to the destination file in WinMerge

His way

  1. Open WinMerge to diff
  2. See the conflicting part
  3. Opens the source file in Windows notepad
  4. Copies the entire contents to clipboard
  5. <div class="msg Nth">
      Opens a new tab in Notepad++
    </div>

  6. Pastes the contents
  7. Goes to the line to be corrected.
  8. Corrects it.
  9. Copies it.
 10. Pastes the line in Notepad.
 11. Saves.<figure style="width: 372px" class="wp-caption aligncenter">

[<img src="https://i1.wp.com/i.stack.imgur.com/fTewC.jpg?resize=372%2C479" alt="What is this I don't even.." width="372" height="479" data-recalc-dims="1" />][1]<figcaption class="wp-caption-text">What is this I don&#8217;t even&#8230;.</figcaption></figure> 

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2014/08/12/an-indian-developers-way-of-handling-merge-conflict/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1264" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2014/08/12/an-indian-developers-way-of-handling-merge-conflict/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1264" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2014/08/12/an-indian-developers-way-of-handling-merge-conflict/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1264" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2014/08/12/an-indian-developers-way-of-handling-merge-conflict/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2014/08/12/an-indian-developers-way-of-handling-merge-conflict/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: https://i1.wp.com/i.stack.imgur.com/fTewC.jpg