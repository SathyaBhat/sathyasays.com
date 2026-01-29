+++
title = "It's Always DNS Part N - Incorrect LAN Interface Edition"
author = "Sathyajith Bhat"
type = "post"
date = 2025-01-29
url = "its-always-dns-part-n"
summary = "Here's how a LAN cable swap broke my Internet connection."
categories = ["Linux", "Arch Linux", "Pacman"]
tags = ["linux", "nas", "dns", "networking" ]
featureimage = "https://i.sathyabh.at/ss/thumb-dns.jpg"
+++

I've been running [AdGuard Home](https://adguard.com/en/adguard-home/overview.html) on my NAS since [about three years now](http://sathyabh.at/nas). It's been running pretty smoothly all this while. Recently, I moved houses and as part of the move, I had to unplug everything and then replug everything back together. After putting everything back together, everything seemed to work okay. Phew, yay! Move complete, no troubles.

One of the rooms was designated as Jo's office space, and that was the room where the [NBN][^1] [NTD][^2] was placed. Jo asked if her desktop could be hardwired via the Ethernet cable, instead of WiFi, and it made sense - I could draw the cable from the router directly to her desktop.

The spare LAN cable that I had was too short to reach her desktop. The LAN cable from the router into my NAS(which was placed right next to the router) is pretty long and would be sufficient to connect directly to her desktop. I swapped the two cables - replaced the LAN cable going into the NAS with the shorter one, while plugging in the longer one into her desktop. Once again, everything seemed to be okay. Things were working fine.

When I come and sat on my desktop, I see the Internet on my desktop had stopped working - DNS resolution was failing. That completely confused me. On all my other devices, the DNS was working fine. I look at the DNS config and it's pointing to the right thing and then I'm like "what is going on?" I plug in, I try to SSH into the NAS and that's timing out. I had my iPad right next to me and check the NAS is working as expected. On the devices connected page opf the router, I see that the LAN IP for the NAS has changed. That confused me again because I put in an IP reservation for the NAS. 

And then it dawned on me - my NAS actually has two LAN ports, so there are two interfaces. When I plugged in the LAN cable when I was doing the swap around, I plugged into the second LAN interface which didn't have the IP reservation set, thus the NAS got a different IP.

For most of the devices in my home, they are configured with the NAS IP set to the primary DNS, with a alternative DNS set to Cloudflare's 1.1.1.1.  This is so that if AdGuard crashes/malfunctions, or if the NAS is not available, the Internet connection in the house doesn't ground to a halt. For my desktop, however, the NAS's IP was set as the only DNS resolver. That's how I found out that my DNS was actually not working as expected and all it was because I plugged into the wrong port. Here's another case of it's always DNS part N.

:-)

[^1]: National Broadband Network
[^2]: Network Termination Device