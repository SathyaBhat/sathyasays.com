---
title: "Implementing and Triggering Google Now Cards & Gmail actions from Email"
author: Sathyajith Bhat
type: post
date: 2016-05-03T10:43:47+00:00
url: /2016/05/03/implementing-and-triggering-google-now-cards-gmail-actions-from-email/
categories:
  - "Tips & How-To's"
tags:
  - programmming
---

For every Barcamp event that comes and goes by, I try to think of what new thing I can do to make it a bit better. Off late, I've been using Inbox by Gmail almost exclusively. I love the product, particularly for the cards that show up that gives you a brief info about the mail(ex: Event reservation details/Flight details etc) without even opening the email.

I noticed that Meetup does the same. So I thought to myself, why not implement this for the mailer we send out to folks who have RSVP'd for the event? We do sent a short &#8216;here's what you should look forward to' email, it'd be cool to add the event details so that people using Google Now would get notification and the Now card as well.

The biggest problem when I started looking out was that I didn't even know what they were known as! After bit of searching with various keywords ("triggering Google now cards", "Inbox cards", "Inbox mail preview") I found that the actual term is "[Gmail actions][1]". Gmail actions use markup from <a href="https://schema.org" target="_blank">schema.org</a> for powering these snippets.

The good thing is that a single markup is enough to power the various places the cards summary will be shown:

- Highlights in Inbox
- Gmail actions
- Google Now cards
- Calendar event based on Gmail

Google has a clear demarcation between Actions and Highlights - Actions are when you need to do something(for example: Confirm/cancel reservations) which Highlights are what you will see on Inbox by Gmail and the Google Now cards.

Furthermore, actions can be InApp actions the most common example is how you can opt to unsubscribe from mailing list without having to go to the site, enter your email and again confirm these). Using the provided markup, you can define how these actions can be handled. Google has extensive documentation on how to handle these, I'd recommend reading these to give <a href="https://developers.google.com/gmail/markup/actions/handling-action-requests" target="_blank">you an idea of how to proceed</a>.

### Writing the Markup

The markup is actually pretty simple and Google gives you an option to write it in JSON-LD or Microdata. Google gives templates for different events:

- <a href="https://developers.google.com/gmail/markup/reference/event-reservation#use_cases" target="_blank">Event Reservation</a>
- <a href="https://developers.google.com/gmail/markup/reference/flight-reservation" target="_blank">Flight Reservation</a>
- <a href="https://developers.google.com/gmail/markup/reference/hotel-reservation" target="_blank">Hotel Reservations</a>

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

- Make sure you meet all <a href="https://developers.google.com/gmail/markup/registering-with-google#registration_guidelines" target="_blank">guidelines listed</a>, especially that your email address is authenticated with SPF check/DKIM signatures. See <a href="https://support.google.com/mail/answer/180707?hl=en" target="_blank">this guide</a> for more info. Don't even bother if SPF/DKIM is not set.
- Google mentions "Consistent history of sending a high volume of mail from your domain (order of hundred emails a day minimum to Gmail) for a few weeks at least" - though we send thousands of mails, especially when a new event is announced, I don't think this is that high of a requirement.
- All that matters that your sending quality should be high, zero(or minimal) complaints and <a href="https://support.google.com/mail/bin/answer.py?hl=en&answer=81126" target="_blank">Bulk Sender Guidelines adhered to</a>.

### Markup from Barcamp Bangalore

This was the markup that I finally used.

```json

  {
      "@context":https://schema.org",
      "@type":EventReservation",
      "reservationNumber":30042016017",
      "reservationStatus":https://schema.org/Confirmed",
      "underName":{
          "@type":Person",
          "name":"[FIRST_NAME]"
      },
      "reservationFor":{
          "@type":Event",
          "name":Barcamp Bangalore Spring 2016",
          "startDate":2016-04-30T08:00:00+05:30",
          "location":{
              "@type":Place",
                  "name":CMR Institute of Technology",
                  "address":{
                      "@type":PostalAddress",
                      "streetAddress":No. 132, AECS Layout, ITPL Main Road, Kundalahalli",
                      "addressLocality":Bangalore",
                      "addressRegion":Karnataka",
                      "postalCode":560037",
                      "addressCountry":in"
                  }
              }
          }
  }
```

### How long till production?

Google took about 7 days to respond to my application, and I had given up hope that I could get the whitelisting done on time - only to be pleasantly surprised and see that it was ready when the mailers were sent.

### So how did it look like?

This is how it ended up looking like across devices:<figure id="attachment_1401" aria-describedby="caption-attachment-1401" style="width: 720px" class="wp-caption aligncenter">

[<img class=" wp-image-1401" src="https://i.sathyabh.at/ss/2016/05/Pasted-image-at-2016_04_29-03_26-PM.png" alt="Inbox Web app"   />][2]<figcaption id="caption-attachment-1401" class="wp-caption-text">**Inbox Web app**</figcaption></figure> <figure id="attachment_1402" aria-describedby="caption-attachment-1402" style="width: 720px" class="wp-caption aligncenter">[<img class=" wp-image-1402" src="https://i.sathyabh.at/ss/2016/05/Screenshot_20160429-165708.png" alt="Inbox Android App"   />][3]<figcaption id="caption-attachment-1402" class="wp-caption-text">**Inbox Android App**</figcaption></figure>

&nbsp;<figure id="attachment_1403" aria-describedby="caption-attachment-1403" style="width: 720px" class="wp-caption aligncenter">

[<img class=" wp-image-1403" src="https://i.sathyabh.at/ss/2016/05/Screenshot_20160430-060054.png" alt="Google Now Card"   />][4]<figcaption id="caption-attachment-1403" class="wp-caption-text">**Google Now Card**</figcaption></figure>

Overall, I was pretty happy with this. I know there aren't too many Inbox by Gmail users, but for the few folks that do use, this looks pretty good and is quite handy

[1]: https://developers.google.com/gmail/markup/actions/actions-overview
[2]: https://i.sathyabh.at/ss/2016/05/Pasted-image-at-2016_04_29-03_26-PM.png
[3]: https://i.sathyabh.at/ss/2016/05/Screenshot_20160429-165708.png
[4]: https://i.sathyabh.at/ss/2016/05/Screenshot_20160430-060054.png
