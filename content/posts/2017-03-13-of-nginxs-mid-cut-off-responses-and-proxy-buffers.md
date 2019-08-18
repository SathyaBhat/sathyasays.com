---
title: Of nginx’s mid cut off responses and proxy buffers
author: Sathya
type: post
date: 2017-03-13T11:50:03+00:00
url: /2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/
categories:
  - "Tips &amp; How-To's"
tags:
  - DevOps
  - nginx
  - opslyfe
  - proxy buffrers
  - reverse proxy

---
Among the services I look after, the biggest and high-profile &#8211; is the user facing website. The website is your bog-standard typical frontend(powered by Express/Angular) which fetches data via an API which is powered by the backend(built on Rails). Typical flow is that Express receives the request from the browser, makes a request to the backend which is then served using Rails API via nginx which acts as the reverse proxy.

<!--more-->

Couple of weeks back, the team received a support request that one specific route from an internal webapp(of similar architecture as the user facing website above) was throwing an 500 Internal Server error. Now in our case, a 500 server error is typically a sign that the backend was not able to complete the request successfully. I took a look at the application logs and the responses were all proper, nothing out of the ordinary. The error would come intermittently and since it was not a route that was heavily in use, I opted to have a deferred look at it.

A few days ago, the same problem manifested again but on a different route(this time, a more frequently used one) and I couldn&#8217;t afford to delay looking at this any longer.

I did some basic analysis:

  * The DB returns the data properly
  * Rails objects are correctly populated
  * The API returns the data
  * Browser console didn&#8217;t show any errors

So what was it that was causing the problem? I tried to make the same request with cURL and this time, I noticed that the API&#8217;s JSON response was truncated and not complete. This was something I didn&#8217;t notice earlier. Since it&#8217;s nginx which is doing the last-mile delivery, I checked nginx error logs there were a few of these:

`[crit] 14606#0: *1562074 open() "/var/lib/nginx/proxy/7/02/0000000027" failed (13: Permission denied) while reading upstream, client: x.x.x.x, server: , request: "GET / HTTP/1.1", upstream: "xx", host: "xxxx"`

Ah ha, now we have something to look for. But why the permission denied while reading upstream? Some Google searching and looking at the documents and nginx forums indicated that the proxy buffer was getting full and hence was not able to send the complete response, hence the truncated JSON responses.

Data from the responses that were cut-off showed that anything over 64kB was getting cut off, indicating the proxy buffer size was set to 64kB. But this was not defined in the nginx configuration anywhere. Some more digging <a href="http://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_buffers" target="_blank" rel="noopener noreferrer">around the documentation</a> indeed confirmed that the buffer size was set to 64kB.

A small fix to increase the buffer size, a deploy via Chef and we&#8217;re all good again.

Some more reading:

  * <a href="http://stackoverflow.com/questions/10557927/server-response-gets-cut-off-half-way-through" target="_blank" rel="noopener noreferrer">Stack Overflow</a>
  * <a href="https://forum.nginx.org/read.php?2,223845,223929#msg-223929" target="_blank" rel="noopener noreferrer">Nginx Forums: Is proxy_buffering needed?</a>
  * <a href="http://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_buffering" target="_blank" rel="noopener noreferrer">Nginx Documentation: Proxy Buffering</a>

Moral of the story: know your platform defaults and keep revisiting your configuration settings, especially if they weren&#8217;t done by you/done long back!

&nbsp;

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1509" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1509" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1509" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2017/03/13/of-nginxs-mid-cut-off-responses-and-proxy-buffers/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>