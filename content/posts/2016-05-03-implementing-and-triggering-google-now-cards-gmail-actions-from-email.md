---
title: 'Implementing and Triggering Google Now Cards & Gmail actions from Email'
author: Sathya
type: post
date: 2016-05-03T10:43:47+00:00
url: /2016/05/03/implementing-and-triggering-google-now-cards-gmail-actions-from-email/
bfa_virtual_template:
  - hierarchy
categories:
  - "Tips & How-To's"
tags:
  - Barcamp Bangalore
  - Gmail Actions
  - Google Now
  - json-ld
  - microdata
  - structured data

---
For every Barcamp event that comes and goes by, I try to think of what new thing I can do to make it a bit better. Off late, I've been using <a href="https://www.google.co.in/inbox/" target="_blank">Inbox by Gmail</a> almost exclusively. I love the product, particularly for the cards that show up that gives you a brief info about the mail(ex: Event reservation details/Flight details etc) without even opening the email.

I noticed that Meetup does the same. So I thought to myself, why not implement this for the mailer we send out to folks who have RSVP'd for the event? We do sent a short &#8216;here's what you should look forward to' email, it'd be cool to add the event details so that people using Google Now would get notification and the Now card as well.

The biggest problem when I started looking out was that I didn't even know what they were known as! After bit of searching with various keywords (&#8220;triggering Google now cards&#8221;, &#8220;Inbox cards&#8221;, &#8220;Inbox mail preview&#8221;) I found that the actual term is &#8220;[Gmail actions][1]&#8220;. Gmail actions use markup from <a href="https://schema.org" target="_blank">schema.org</a> for powering these snippets.

<!--more-->

The good thing is that a single markup is enough to power the various places the cards summary will be shown:

  * Highlights in Inbox
  * Gmail actions
  * Google Now cards
  * <a href="https://developers.google.com/gmail/markup/google-calendar#an-event-booking" target="_blank">Calendar event based on Gmail</a>

Google has a clear demarcation between Actions and Highlights &#8211; Actions are when you need to do something(for example: Confirm/cancel reservations) which Highlights are what you will see on Inbox by Gmail and the Google Now cards.

Furthermore, actions can be <a href="https://developers.google.com/gmail/markup/actions/actions-overview#in-app_actions" target="_blank">InApp actions</a> &#8211; the most common example is how you can opt to unsubscribe from mailing list without having to go to the site, enter your email and again confirm these). Using the provided markup, you can define how these actions can be handled. Google has extensive documentation on how to handle these, I'd recommend reading these to give <a href="https://developers.google.com/gmail/markup/actions/handling-action-requests" target="_blank">you an idea of how to proceed</a>.

### Writing the Markup

The markup is actually pretty simple and Google gives you an option to write it in JSON-LD or Microdata. Google gives templates for different events:

  * <a href="https://developers.google.com/gmail/markup/reference/event-reservation#use_cases" target="_blank">Event Reservation</a>
  * <a href="https://developers.google.com/gmail/markup/reference/flight-reservation" target="_blank">Flight Reservation</a>
  * <a href="https://developers.google.com/gmail/markup/reference/hotel-reservation" target="_blank">Hotel Reservations</a>

and many, many others that you can use. Check <a href="https://developers.google.com/gmail/markup/reference/" target="_blank">Google's Reference guides here</a>. I used JSON-LD because it seemed more intuitive concise to me.

### Extracting the markup

Alternatively, if you don't wish to write the Markup, Google offers a way where you can post the HTML of the email and it will attempt to <a href="https://www.google.com/webmasters/markup-helper/u/0/?" target="_blank">extract the structured data and generate the Markup</a>. This approached worked fairly well, though I'd still suggest you write the Markup by yourself with the help of existing templates.

### Validating the Markup

Simply writing the markup isn't enough, you will need to validate the markup, else Google will reject your application for whitelisting(will mention this later). Thankfully, Google provides a <a href="https://www.google.com/webmasters/markup-tester/u/0/" target="_blank">Markup validator </a>to ensure that your Markup is correct.

### Testing the Markup

Since these markups need to be registered, validated and whitelisted by Google, you cannot simply whip up an email from your production server and send an email to your test account. However, you can test for these integrations by creating an email containing the final Markup and send it to yourself. Since these emails need to be in HTML format, you can not use Gmail webapp. You can use <a href="https://developers.google.com/gmail/markup/apps-script-tutorial" target="_blank">this Google Apps Script</a> or the <a href="https://gmail-actions.appspot.com/" target="_blank">Gmail Actions Email app to send emails</a> to yourself. Alternatively, an HTML mail from desktop mail clients should also work(though I have not tested).

### All set for production run!

Well, not quite. Google needs to whitelist your email address before these actions/highlights can be seen in your emails. You will need to send an email from your production server to <schema.whitelisting+sample@gmail.com> and <a href="https://docs.google.com/a/google.com/forms/d/1PA-vjjk3yJF7MLPOVKbIz3MBfhyma2obS8NIZ0JYx8I/viewform?pli=1" target="_blank">fill in the registration form</a>.

Tips for getting whitelisted:

  * Make sure you meet all <a href="https://developers.google.com/gmail/markup/registering-with-google#registration_guidelines" target="_blank">guidelines listed</a>, especially that your email address is authenticated with SPF check/DKIM signatures. See <a href="https://support.google.com/mail/answer/180707?hl=en" target="_blank">this guide</a> for more info. Don't even bother if SPF/DKIM is not set.
  * Google mentions &#8220;Consistent history of sending a high volume of mail from your domain (order of hundred emails a day minimum to Gmail) for a few weeks at least&#8221; &#8211; though we send thousands of mails, especially when a new event is announced, I don't think this is that high of a requirement.
  * All that matters that your sending quality should be high, zero(or minimal) complaints and <a href="https://support.google.com/mail/bin/answer.py?hl=en&answer=81126" target="_blank">Bulk Sender Guidelines adhered to</a>.

### Markup from Barcamp Bangalore

This was the markup that I finally used.

> <pre><span class="o">&lt;</span><span class="nx">script</span> <span class="nx">type</span><span class="o">=</span><span class="s2">"application/ld+json"</span><span class="o">&gt;</span>
    <span class="p">{</span>
        <span class="s2">"@context"</span><span class="o">:</span>                     <span class="s2">"https://schema.org"</span><span class="p">,</span>
        <span class="s2">"@type"</span><span class="o">:</span>                        <span class="s2">"EventReservation"</span><span class="p">,</span>
        <span class="s2">"reservationNumber"</span><span class="o">:</span>            <span class="s2">"30042016017"</span><span class="p">,</span>
        <span class="s2">"reservationStatus"</span><span class="o">:</span>            <span class="s2">"https://schema.org/Confirmed"</span><span class="p">,</span>
        <span class="s2">"underName"</span><span class="o">:</span> <span class="p">{</span>
            <span class="s2">"@type"</span><span class="o">:</span>                    <span class="s2">"Person"</span><span class="p">,</span>
            <span class="s2">"name"</span><span class="o">:</span>                     <span class="s2">"[FIRST_NAME]"</span>
        <span class="p">},</span>
        <span class="s2">"reservationFor"</span><span class="o">:</span> <span class="p">{</span>
            <span class="s2">"@type"</span><span class="o">:</span>                    <span class="s2">"Event"</span><span class="p">,</span>
            <span class="s2">"name"</span><span class="o">:</span>                     <span class="s2">"Barcamp Bangalore Spring 2016"</span><span class="p">,</span>
            <span class="s2">"startDate"</span><span class="o">:</span>                <span class="s2">"2016-04-30T08:00:00+05:30"</span><span class="p">,</span>
            <span class="s2">"location"</span><span class="o">:</span> <span class="p">{</span>
                <span class="s2">"@type"</span><span class="o">:</span> <span class="s2">"Place"</span><span class="p">,</span>
                    <span class="s2">"name"</span><span class="o">:</span> <span class="s2">"CMR Institute of Technology"</span><span class="p">,</span>
                    <span class="s2">"address"</span><span class="o">:</span> <span class="p">{</span>
                        <span class="s2">"@type"</span><span class="o">:</span>                <span class="s2">"PostalAddress"</span><span class="p">,</span>
                        <span class="s2">"streetAddress"</span><span class="o">:</span>        <span class="s2">"No. 132, AECS Layout, ITPL Main Road, Kundalahalli"</span><span class="p">,</span>
                        <span class="s2">"addressLocality"</span><span class="o">:</span>      <span class="s2">"Bangalore"</span><span class="p">,</span>
                        <span class="s2">"addressRegion"</span><span class="o">:</span>        <span class="s2">"Karnataka"</span><span class="p">,</span>
                        <span class="s2">"postalCode"</span><span class="o">:</span>           <span class="s2">"560037"</span><span class="p">,</span>
                        <span class="s2">"addressCountry"</span><span class="o">:</span>       <span class="s2">"in"</span>
                    <span class="p">}</span>
                 <span class="p">}</span>
            <span class="p">}</span>
        <span class="p">}</span>
    <span class="o">&lt;</span><span class="err">/script&gt;</span></pre>

### How long till production?

Google took about 7 days to respond to my application, and I had given up hope that I could get the whitelisting done on time &#8211; only to be pleasantly surprised and see that it was ready when the mailers were sent.

### So how did it look like?

This is how it ended up looking like across devices:<figure id="attachment_1401" aria-describedby="caption-attachment-1401" style="width: 720px" class="wp-caption aligncenter">

[<img class=" wp-image-1401" src="https://sathyasays.com/wp-content/uploads/2016/05/Pasted-image-at-2016_04_29-03_26-PM.png" alt="Inbox Web app"   />][2]<figcaption id="caption-attachment-1401" class="wp-caption-text">**Inbox Web app**</figcaption></figure> <figure id="attachment_1402" aria-describedby="caption-attachment-1402" style="width: 720px" class="wp-caption aligncenter">[<img class=" wp-image-1402" src="https://sathyasays.com/wp-content/uploads/2016/05/Screenshot_20160429-165708.png" alt="Inbox Android App"   />][3]<figcaption id="caption-attachment-1402" class="wp-caption-text">**Inbox Android App**</figcaption></figure> 

&nbsp;<figure id="attachment_1403" aria-describedby="caption-attachment-1403" style="width: 720px" class="wp-caption aligncenter">

[<img class=" wp-image-1403" src="https://sathyasays.com/wp-content/uploads/2016/05/Screenshot_20160430-060054.png" alt="Google Now Card"   />][4]<figcaption id="caption-attachment-1403" class="wp-caption-text">**Google Now Card**</figcaption></figure> 

Overall, I was pretty happy with this. I know there aren't too many Inbox by Gmail users, but for the few folks that do use, this looks pretty good and is quite handy

 [1]: https://developers.google.com/gmail/markup/actions/actions-overview
 [2]: https://sathyasays.com/wp-content/uploads/2016/05/Pasted-image-at-2016_04_29-03_26-PM.png
 [3]: https://sathyasays.com/wp-content/uploads/2016/05/Screenshot_20160429-165708.png
 [4]: https://sathyasays.com/wp-content/uploads/2016/05/Screenshot_20160430-060054.png
