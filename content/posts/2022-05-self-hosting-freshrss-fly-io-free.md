---
title: Self-hosting FreshRSS (for free) on Fly.io in under 10 minutes
author: Sathyajith Bhat
type: post
date: 2022-09-05
url: /2022/09/05/self-hosting-freshrss-fly-io-free
description: Here's how you can self-host FreshRSS on Fly.io in under 10 minutes
featured_image: https://i.sathyabh.at/ss/fly-dot-io-logo.svg
meta_image: https://i.sathyabh.at/ss/fly-dot-io-logo.svg
categories:
  - DevOps
tags:
  - Self-hosting
  - Fly.io
---
### Running FreshRSS on Fly.io

[FreshRSS](https://www.freshrss.org/) is a free, self-hostable RSS feeds aggregator. [Fly.io](https://fly.io/) is a super amazing platform that runs application servers close to end users. 

Fly.io can take Docker images (or Dockerfiles, or buildpacks) and boot them into [Firecracker](https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/) powered microVMs. When you deploy with Fly.io, you get an Anycast IP, along with TLS offloading by them. The Firecracker microVMs can scale up & down per traffic, and it comes with a [pretty generous free tier](https://fly.io/docs/about/pricing/) that includes

* Up to 3 shared-cpu-1x 256MB VMs
* 3GB of total persistent volume storage 
* 160GB outbound data transfer

Since FreshRSS comes with a Docker image, adapting it to fly.io was as straightforward as pointing to FreshRSS' Docker image. These are the steps if you wish to run FreshRSS on your fly.io account

* Sign up for [Fly.io](https://fly.io/) or sign-in
* Install [flyctl](https://fly.io/docs/hands-on/install-flyctl/)
* Sign into your Fly.io account by typing `flyctl auth login`
* Create a `fly.toml` file similar to the one in [my repo](https://github.com/SathyaBhat/freshrss-on-fly-io). Make sure to update the appname to a unique name.
* Review the environment variables listed in the `[env]` section and update if required. You can check [FreshRSS' docs](https://github.com/FreshRSS/FreshRSS/blob/edge/Docker/freshrss/example.env) on the environment variables that can be updated 
* Create a volume for persisting data using the command `fly volumes create freshrss_data --size 1`
    * In this command, we create a volume of size 1GB. This can be increased later, so I selected the lowest possible number, as flyctl expects size in GB and doesn't accept fractional numbers.
* Save the `fly.toml` file. From the same directory where `fly.toml` is present, deploy FreshRSS the application using `fly launch`. Fly.io will pull the Docker image and launch the VM. The output should be as shown below: 

```bash

fly launch
An existing fly.toml file was found for app freshrss
App is not running, deploy...
Deploying freshrss
==> Validating app configuration
--> Validating app configuration done
Services
TCP 80/443 ⇢ 80
Searching for image 'freshrss/freshrss' remotely...
image found: img_lj9x4d7jkwe4wo1k
Image: registry-1.docker.io/freshrss/freshrss:latest
Image size: 75 MB
==> Creating release
Release v1 created

You can detach the terminal anytime without stopping the deployment
Monitoring Deployment

1 desired, 1 placed, 1 healthy, 0 unhealthy
--> v1 deployed successfully
```

That's it! FreshRSS should be accessible from the URL `<appname>.fly.dev`. You can front a custom domain as well. Head over to the Certificates tab from Fly.io's dashboard, or use the `flyctl` tool to provision a certificate by typing `flyctl certs add <domain>`. Add the CNAME that Fly tells you about, and then add an A record for the (sub)domain, pointing to the Anycast IP you get from deploying FreshRSS. See [Fly.io's docs](https://fly.io/docs/app-guides/custom-domains-with-fly/#creating-a-custom-domain-on-fly-manually) on how to do this.


### Caveats

* FreshRSS extensions need to be available on `/var/www/FreshRSS/extensions`, however - Fly.io doesn't support having [same mount for mulitple directories](https://community.fly.io/t/mount-multiple-destinations-to-the-same-source-volume/5298), or having [multiple mounts](https://community.fly.io/t/multiple-mounts-in-one-app/4701). 
    * Trying to mount just `/var/www/FreshRSS` caused the microVM to throw kernel panics, mainly because the underlying Docker container expects _something_ there - probably the webserver config and mounting an empty VM causes errors
    * You could try to play with Fly's internal networking, including [setting up a wireguard tunnel](https://community.fly.io/t/how-to-copy-files-off-a-vm/1651/13), but I didn't try.
    * Another icky way is to build a custom Dockerfile copying the required extensions into the image during the build step.. 
* I haven't run this for long, will update if I run into issues

### Automated updates and deploys 

Fly.io's CLI-oriented approach makes updates via GitHub actions easy. While I haven't set up for FreshRSS, you can look at [this PR](https://github.com/SathyaBhat/sathyabh.at/pull/37) where I add a GitHub action to deploy my blog, [sathyabh.at](https://sathyabh.at), a static site powered by Hugo to Fly.io. 

Fly.io's [community Discourse](https://community.fly.io/) is quite active if you run into any problems. Hope this gives you a good taste of what Fly.io can offer.

See also: [Github repo](https://github.com/SathyaBhat/freshrss-on-fly-io) of the fly.io config file.