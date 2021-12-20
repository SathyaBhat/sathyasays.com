---
title: 'When you get bit by precision & scale in PL/SQL…'
author: Sathyajith Bhat
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

In this specific case, the date of birth was 05.01.1951 and start date was 01.01.2016 - the expected age that was to be returned(after round off to 4) was 64.9892. The application, however was returning 65.  I went through the log, the dates are proper. I went through the source, the round off is indeed to 4 places but still it was returning 65. I ran the bit of code responsible for fetching and calculating outside in couple of editors, including Toad & SQL*Plus, and both cases it was returning 64.9892 - and now I was flummoxed - where and why the heck was it rounding off?

I thought for a bit, asked my colleagues and we were at a loss. All set to ask on Stack Overflow, I suddenly had a revelation and looked at the declaration section. And indeed, it problem was there:

<pre style="padding-left: 30px;">n_age NUMBER(8);
</pre>

The variable holding the age had a precision applied. The documentation mentions:

> You can also specify a precision (total number of digits) [..]. If a precision is not specified, the **column stores values as given. If no scale is specified, the scale is zero.**.
> 
> &nbsp;

With no scale mentioned, the number would get a &#8216;free' rounding off and store an incorrect value. The small things that bite..
