---
title: 'When you get bit by precision & scale in PL/SQL…'
author: Sathya
type: post
date: 2016-01-05T06:37:59+00:00
url: /2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/
bfa_virtual_template:
  - hierarchy
categories:
  - Programming
tags:
  - oracle
  - pl/sql

---
I got a bug assigned to me where my application was returning an incorrect value. Some background: The function was an age check function which takes in date of birth & start date and returns the age.

In this specific case, the date of birth was 05.01.1951 and start date was 01.01.2016 &#8211; the expected age that was to be returned(after round off to 4) was 64.9892. The application, however was returning 65.  I went through the log, the dates are proper. I went through the source, the round off is indeed to 4 places but still it was returning 65. I ran the bit of code responsible for fetching and calculating outside in couple of editors, including Toad & SQL*Plus, and both cases it was returning 64.9892 &#8211; and now I was flummoxed &#8211; where and why the heck was it rounding off?

I thought for a bit, asked my colleagues and we were at a loss. All set to ask on Stack Overflow, I suddenly had a revelation and looked at the declaration section. And indeed, it problem was there:

<pre style="padding-left: 30px;">n_age NUMBER(8);
</pre>

The variable holding the age had a precision applied. The documentation mentions:

> You can also specify a precision (total number of digits) [..]. If a precision is not specified, the **column stores values as given. If no scale is specified, the scale is zero.**.
> 
> &nbsp;

With no scale mentioned, the number would get a &#8216;free&#8217; rounding off and store an incorrect value. The small things that bite..

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1350" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1350" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1350" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2016/01/05/when-you-get-bit-by-precision-scale-in-plsql/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>