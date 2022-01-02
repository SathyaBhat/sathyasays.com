---
title: An Indian developer’s way of handling merge conflict
author: Sathyajith Bhat
type: post
date: 2014-08-12T06:15:25+00:00
url: /2014/08/12/an-indian-developers-way-of-handling-merge-conflict/
categories:
  - Programming


---
So this happened just now with a colleague. He's been working for few months now.

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

[<img src="https://i.stack.imgur.com/fTewC.jpg" alt="What is this I don't even.."   />][1]<figcaption class="wp-caption-text">What is this I don't even&#8230;.</figcaption></figure>

 [1]: https://i.stack.imgur.com/fTewC.jpg
