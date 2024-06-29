---
title: An Indian developer’s way of handling merge conflict
author: Sathyajith Bhat
type: post
date: 2014-08-12T06:15:25+00:00
url: /2014/08/12/an-indian-developers-way-of-handling-merge-conflict/
categories:
  - Programming
tags:
  - rants
  - git

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
  5. Opens a new tab in Notepad++
  6. Pastes the contents
  7. Goes to the line to be corrected.
  8. Corrects it.
  9. Copies it.
 10. Pastes the line in Notepad.
 11. Saves.
 
 ![What is this I don't even..][1]
 

 [1]: https://i.stack.imgur.com/fTewC.jpg
