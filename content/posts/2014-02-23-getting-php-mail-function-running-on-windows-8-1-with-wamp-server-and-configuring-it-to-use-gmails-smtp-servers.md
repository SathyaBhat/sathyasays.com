---
title: Getting php mail() function running on Windows 8.1 with WAMP Server and configuring it to use Gmail’s SMTP servers
author: Sathyajith Bhat
type: post
date: 2014-02-23T14:52:29+00:00
url: /2014/02/23/getting-php-mail-function-running-on-windows-8-1-with-wamp-server-and-configuring-it-to-use-gmails-smtp-servers/
evolve_slider_type:
  - no
categories:
  - "Tips & How-To's"
tags:
  - PHP
  - sendmail

---
With the next <a href="https://barcampbangalore.org/" target="_blank">Barcamp Bangalore</a> looming round the corner, I'd pitched in to help with some of the website tasks. I installed the traditional WAMP stack with <a href="https://www.wampserver.com/en/" target="_blank">WAMP Server for Windows</a> and started working with WordPress. Needed to get the email notifications working, saw that it wasn't. Bit of research & found that I'd need a SMTP server or an equivalent of sendmail.

All the cool kids seem to be using <a href="https://glob.com.au/sendmail/" target="_blank">Fake sendmail</a> - I tried it to use with Gmail's SMTP servers which uses authentication & TLS. Fake sendmail either would crash repeatedly or give a Socket Error # 10060 Connection timed out error.

Finally, after much trawling the Intarwebz, going through many forums & Stack Overflow posts, finally found <a href="https://yogeshchaugule.com/blog/2013/configure-sendmail-wamp" target="_blank">this blog post</a> which recommends using stunnel.

So this is what my php.ini settings look like:


```
[mail function]
; For Win32 only.
; https://php.net/smtp
;SMTP = localhost
; https://php.net/smtp-port
;smtp_port = 25

; For Win32 only.
; https://php.net/sendmail-from

sendmail_from = <the gmail id>

;C:\wamp\bin\sendmail
; For Unix only. You may supply arguments as well (default: "sendmail -t -i").
; https://php.net/sendmail-path

sendmail_path = "C:\wamp\bin\sendmail\sendmail.exe -t"
```

Yes, all parameters, except for `sendmail_form` & `sendmail_path` are commented. They are set in sendmail.ini & stunnel.

sendmail.ini:

```bash
smtp_server=localhost
smtp_port=25

; SMTPS (SSL) support
; auto = use SSL for port 465, otherwise try to use TLS
; ssl = alway use SSL
; tls = always use TLS
; none = never try to use SSL
smtp_ssl=none

auth_username=gmail username
auth_password=gmail password
```

stunnel.conf

```bash
; Certificate/key is needed in server mode and optional in client mode
cert = stunnel.pem
socket = l:TCP_NODELAY=1
socket = r:TCP_NODELAY=1
key = stunnel.pem

[ssmtp]
accept  = 465
connect = 25

[gmail-smtp]
client = yes
accept = 127.0.0.1:25
connect = smtp.gmail.com:465
```