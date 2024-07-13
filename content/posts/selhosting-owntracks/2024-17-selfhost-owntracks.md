---
title: Self-hosting your location history with OwnTracks 
author: Sathyajith Bhat
type: post
date: 2024-07-13
url: /2024/07/13/self-hosting-owntracks-google-maps-timeline-alternative
summary: Looking to find an alternative to Google Maps Timeline? OwnTracks is a self-hosted location history tracker and might be a decent alternative to Google Maps Timeline.
featureimage: https://i.sathyabh.at/sb/owntracks/owntracks-logo.svg
categories:
  - Self-Hosting
tags:
  - owntracks
  - google maps
---

### Why OwnTracks?

[OwnTracks](https://owntracks.org/) is a private location diary. Think of it as a self-hosted version of Google Maps Timeline. If you're not familiar with Google Maps Timeline, it's a service that tracks your location history and shows your previous routes and places that you've been on based on your location history. I've been using Google Maps Timeline since a long time and have been quite happy with it. 

Recently, Google [announced that they are changing](https://support.google.com/maps/answer/14169818?visit_id=638564387215552617-1652775936&p=maps_odlh&rd=1) the way location history is saved - they will no longer keep the location history tied to your Google Account and the history will be local to the device. Since the history is local to the device, a side effect is the Timeline webapp is also going away. 

I use the Google Maps Timeline web app quite heavily and was disappointed to know it was going away. When looking for alternatives to Timeline, [Rushabh](https://mastodon.social/@rushvora@hachyderm.io) told me about OwnTracks. Since I had upgraded the memory on [my NAS](https://sathyabh.at/nas), I had some extra breathing space and decided to try it out. With my upcoming Seattle trip, I thought this was a great way to test out OwnTracks and see how it compares to Google Maps Timeline.

### What is OwnTracks?

OwnTracks lets you build your private location diary. OwnTracks comes with a server side component to save history and client (mobile) applications that report your location. The client applications report location when the smartphone OS has reported to OwnTracks that it has moved enough. Keep this in mind - OwnTracks doesn't actively poll the current location (at least not on iOS anyway) but rather waits for the mobile OS to report a location change. You can find more details about how the mobile app works in their [documentation booklet](https://owntracks.org/booklet/features/location/). 

On the server side, OwnTracks has a component called the Recorder that stores the location data. The applications talk to the Recorder via an MQTT or HTTP call and the Recorder stores the data in plaintext files. The Recorder primarily uses MQTT as its protocol, but OwnTracks has implemented an HTTP server that clients can talk to. The OwnTracks architecture looks like this below.

![owntracks architecture][ot-arch]


### Setting up OwnTracks using Docker

OwnTracks has a nice repo called [`quicksetup`][quicksetup] that helps you get started. However, the quick setup is targetted at setting up OwnTracks on a VPS to run OwnTracks recorder, a mosquitto MQTT broker, and nginx as the reverse proxy. The quicksetup also assumes that nothing else is running and there are no port conflicts, and wasn't suitable for running OwnTracks as containers using Docker. Thankfully, they do build and publish pre-built container images and have a few sample docker-compose configs in the [docker-recorder](https://github.com/owntracks/docker-recorder) repo that we can use. When I set up initially, I was using the basic web UI built into the recorder image. I found out that OwnTracks has a nice frontend SPA that has a lot more features (such as location history, heatmap etc) and thus I decided to use it as well. 

After a couple of iterations, this is the Docker compose file that worked for me:

```yaml
services:
  otrecorder:
    image: owntracks/recorder
    volumes:
      - ./store:/store
    restart: unless-stopped
    environment:
      OTR_HOST: mosquitto
    networks:
      - sanctuary

  frontend:
    image: owntracks/frontend
    volumes:
      - ./frontend/config.js:/usr/share/nginx/html/config/config.js
    restart: unless-stopped
    environment:
      - SERVER_HOST=otrecorder
      - SERVER_PORT=8083
    networks:
      - sanctuary

  mosquitto:
    image: eclipse-mosquitto
    volumes:
      - ./mosquitto/data:/mosquitto/data
      - ./mosquitto/logs:/mosquitto/logs
      - ./mosquitto/conf:/mosquitto/config
    restart: unless-stopped
    networks:
      - sanctuary

networks:
  sanctuary:
    external: true
```

There are a couple of changes I have made from the example Docker compose config files:

* There are no ports published - that is because I use Caddy as the reverse proxy, and Caddy routes the requests to the OwnTrack containers since they're all part of a custom Docker bridge network.
* ~~OwnTracks requires that an MQTT broker be present else it just quits. So even though you may not decide to use the MQTT broker endpoint, it has to be running else the Recorder fails to start. On the nice side, Mosquitto barely consumes any resources so it shouldn't be too much of a bother~~. OwnTracks maintainers [corrected me](https://mastodon.social/@owntracks@fosstodon.org/112779454981041563) and mention that the Recorder does *not* require MQTT; `--port 0` disables the check. 
* I make use of bind mounts to store the data instead of Docker Volumes. 
* `sanctuary` is the external custom Docker bridge network that is attached to all the containers that are accessible by Caddy.
* The mqtt broker doesn't have any auth configured, I am fine with this - you'll have to change this according to your needs.

In addition to the above compose file, I added the following config files:

* `mosquitto.conf` file in  `mosquitto/conf/mosquitto.conf` that configures mosquitto broker to allow anonymous access

``` conf
allow_anonymous true
listener 1883
socket_domain ipv4
```

### Connecting to OwnTracks using Caddy 

I use Caddy as my reverse proxy. My NAS doesn't allow for connections from the outside world and I use Tailscale so that only those devices that are part of my tailnet can connect to the server. The Caddyfile looks like below

* Caddy config file:

```Caddyfile
(config) {

# otrecorder path is used for the recorder/OwnTracks API
  handle_path /otrecorder/* {
    reverse_proxy owntracks-otrecorder-1:8083
  }

# owntracks endpoint used by the OwnTracks frontend SPA
  handle_path /owntracks/* {
    reverse_proxy owntracks-frontend-1:80
  }
}

nas.my-tailnet.ts.net {
  import config
}
```

_*Note:* If you plan to use a similar setup, be sure to replace the URL with your own. Since I cannot use app-specific subdomains using Tailscale's MagicDNS, the endpoint for each application on my tailnet is a subpath which gets reverse proxied to the application containers, and often is a source of pain. In this case, `/otrecorder/` points to OwnTracks Recorder while `/owntracks/` endpoint points to the frontend app._

With these files configured, start the containers by typing:

```bash
# if you have the older version of docker-compose
docker-compose up -d
```

or 

```bash
# if you have the newer version of docker-compose
docker compose up -d
```

You can check the logs and confirm that OwnTracks is running using the below commands

```bash
# if you have the older version of docker-compose
docker-compose logs -f
```
or

```bash
# if you have the newer version of docker-compose
docker compose logs -f
```

The logs should show something like the below to indicate OwnTracks is running as expected

```log
mosquitto-1   | 1720854672: mosquitto version 2.0.18 starting
mosquitto-1   | 1720854672: Config loaded from /mosquitto/config/mosquitto.conf.
mosquitto-1   | 1720854672: Opening ipv4 listen socket on port 1883.
mosquitto-1   | 1720854672: mosquitto version 2.0.18 running
mosquitto-1   | 1720854672: New connection from 172.19.0.15:43446 on port 1883.
mosquitto-1   | 1720854672: New client connected from 172.19.0.15:43446 as ot-recorder-58435cc977cf-7 (p2, c0, k60).
otrecorder-1  | + version 0.9.7 starting with STORAGEDIR=/store
otrecorder-1  | + connecting to MQTT on mosquitto:1883 as clientID ot-recorder-58435cc977cf-7 without TLS
otrecorder-1  | + HTTP listener started on 0.0.0.0:8083, without browser-apikey
otrecorder-1  | + HTTP prefix is unset
otrecorder-1  | + Using storage at /store with precision 7
otrecorder-1  | + TZDATADB is at /config/timezone16.bin: R_OK
otrecorder-1  | + Subscribing to owntracks/# (qos=2)
```
With this config, my devices that have tailscale running can connect to OwnTracks using the `https://nas.my-tailnet.ts.net/otrecorder` endpoint for the OwnTracks API and `https://nas.my-tailnet.ts.net/owntracks` endpoint to load the frontend app.

### Blank map issues with OwnTracks Frontend

When I brought up the containers and navigated to the frontend app on the browser, the frontend SPA was still not loading correctly - the map was blank. I could see that the API was fetching the data correctly, but it was not being drawn on the map. After searching the Owntracks' frontend repo, I came across this issue which described [the problem](https://github.com/owntracks/frontend/issues/89), and thus I updated my `frontend/config.js` file as below to include the basepath

```js
window.owntracks = window.owntracks || {};
window.owntracks.config = {
  api: {
    baseUrl: 'https://nas.my-tailnet.ts.net/otrecorder/',
  },
  router: {
    basePath: '/owntracks',
  },
};
```

and voila, that got things working.  

!["owntracks SPA"][2]

### Configuring Mobile Apps

The mobile apps are not the best designed but they do the job. The confusing part about the mobile apps was configuring them. There's little documentation about it, especially the endpoint path to which OwnTracks app publishes to and I struggled to find the right endpoint. After some furious searching, I found out about the `/pub` [endpoint](https://github.com/owntracks/recorder?tab=readme-ov-file#the-http-server) and that did the job.

So in summary, once you launch the Mobile app, set the following:

* Endpoint: `https://nas.my-tailnet.ts.net/otrecorder/pub` - replace the URL with your own, and don't forget the `/pub` path - that is the most important.
* DeviceID: Set it to a memorable name to identify your device - possibly the name of the phone itself.
* userid: Set to your userid. This is used internally to set the mqtt topic.

Once this is done click on the Publish option and that should let you know if everything's working ok or not.

### Changing location modes automatically

As mentioned above, on the iPhone, OwnTracks doesn't actively poll the location - rather, the app offers [different modes of publishing](https://owntracks.org/booklet/features/location/)

* Quiet mode: Only manual location reports.
* Manual mode: Manual location reports and automated reports with region monitoring.
* Significant mode: iOS defines a Significant location change as traveling a distance of at least 500 meters in 5 minutes.
* Move mode: Frequent location. The app publishes a new location as soon as the device moves 100 meters or after 5 minutes. 

OwnTracks uses Significant as the default mode. This works well, however, if you frequently go to places that are within the threshold mentioned above, then they will not get recorded at all. One way to correct this is to switch to move mode just as you leave the house. However, this can get tedious and was wondering if there's a way to automate this. 

Out of curiosity, I looked at the Shortcuts app to see if OwnTracks has registered the location modes. Guess what, it does! With this, now we can configure Shortcuts with an automation to switch to Move with a "Leave Area" trigger, and another automation to switch back to "Significant" when we arrive at our location.

### Sharing location automatically with Friends and Family

OwnTracks has a friends capability - the way it works is the people who connect to the same MQTT broker can see each other on a map. In theory, this is a good feature. Practically however, configuring friends is tedious - especially when the clients are connected using HTTP mode.

In MQTT mode, OwnTracks do the configuration and subscriptions automatically. In HTTP mode, the Recorder must be manually configured to know about Friends. This requires connecting to the Recorder container (or the host where the Recorder is running) and loading the file manually in the below format, as documneted in the [Recorder readme](https://github.com/owntracks/recorder?tab=readme-ov-file#friends)

> For example, when a user called jane on device phone publishes in http mode and she should be permitted to see where john / android is, we add the following key/value to the friends named database:

```bash
ocat --load=friends <<EOF
jane-phone [ "john/android" ]
EOF
```

Once this has been loaded to the Recorder, each Friend must publish so that the response object with the new list of Friends is sent back and they are shown in the map. Given that OwnTracks is effectively a MQTT pub/sub service, unless configured ahead of time, each person will be shown as a value from TrackerID which seems to be a randomly generated two-character id. So when friends are added en-masse, trying to map TrackerID to a person can be very annoying. The good news is that each TrackerID can be mapped to a person on your Contacts so it's easier to track who's where.

### Final Thoughts

Overall I'm pretty impressed with OwnTracks. Sure, the initial setup is a bit of a pain, but once it's up and running it's been pretty good. The mobile UX could use some improvements, and I wish the web app would get more features, such as being able to search where I was. These minor niggles aside, I would highly recommend giving it a try and see if it works for you.

[ot-arch]: https://i.sathyabh.at/sb/owntracks/owntracks-arch.png
[quicksetup]: https://github.com/owntracks/quicksetup

[2]: https://i.sathyabh.at/sb/owntracks/owntracks-frontend.jpg
