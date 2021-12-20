---
title: Scanning Docker Image for Vulnerabilities with Aqua MicroScanner
author: Sathyajith Bhat
type: post
date: 2018-05-28T18:10:16+00:00
url: /2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/
categories:
  - "Tips & How-To's"
tags:
  - Aqua
  - Clair
  - containers
  - Docker
  - Twistlock
  - vulnerability
  - vulnerability scanner

---
Containers are slowly becoming the standardized units of deployment. As containers become more popular, they also become the focus targets for attacking the system via vulnerabilities present in the packages within the image. There are quite a few container vulnerability scanning solutions (example: [Clair](https://github.com/coreos/clair), [Twistlock, now Prisma Cloud](https://www.twistlock.com), [Aqua](https://www.aquasec.com) – however most of them are either commercial or require an elaborate setup, which makes it difficult for individual developers to involve them as part of the container build process.

<!--more-->

I found recently that Aqua has introduced a free-to-use tool called [Aqua MicroScanner](https://github.com/aquasecurity/microscanner) for scanning container images for package vulnerabilities. What makes this even more attractive and easy-to-use is that it doesn't need any elaborate or predefined server setups – and all that is needed to use this is:

  * Get a token from Aqua
  * Add the scanner and run it as part of the container build process

If the image contains any packages with vulnerabilities, Aqua will present a summary of the vulnerabilities, the average CVE score as well as a list of the found vulnerabilities.

To get started with Aqua MicroScanner, register for a token

    $ docker run --rm -it aquasec/microscanner --register <email address>

With the token available, add it as part of your build process. For example, if we were to check and scan an image based on nginx, the Dockerfile would look like below

``` 
FROM nginx:1-alpine 
RUN apk add --no-cache ca-certificates && update-ca-certificates 
ADD https://get.aquasec.com/microscanner . 
RUN chmod +x microscanner 
RUN ./microscanner <token> 
```
  
When we build the container with

`$ docker build .`

The scanner will be executed and will scan the Docker image. The vulnerability found will be displayed as below
  
```
"vulnerabilities": [ 
{ 
"name": "CVE-2016-3189", 
"description": "Use-after-free vulnerability in bzip2recover in bzip2 1.0.6 allows remote attackers to cause 
a denial of service (crash) via a crafted bzip2 file, related to block ends set to before the start of the block.", 
"nvd_score": 4.3, 
"nvd_score_version": "CVSS v2", 
"nvd_vectors": "AV:N/AC:M/Au:N/C:N/I:N/A:P", 
"nvd_severity": "medium", 
"nvd_url": "https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2016-3189", 
"vendor_score": 4.3, 
"vendor_score_version": "CVSS v2", 
"vendor_vectors": "AV:N/AC:M/Au:N/C:N/I:N/A:P", 
"vendor_severity": "medium", 
"publish_date": "2016-06-30", 
"modification_date": "2017-08-21" 
} 
] 
``` 
  
The summary would be like so:

```
"vulnerability_summary": { 
"total": 2, 
"medium": 2, 
"score_average": 4.3, 
"max_score": 4.3 
} 
```

Aqua will stop the build if it finds any vulnerabilities of severity "High" – however, we can pass  `--continue-on-failure` flag to ignore the High severity issues and continue the build.

I think this tool is really good, especially for small developers – with just few lines of Dockerfile instructions, the developer is able add vulnerability scanning of the images – and combined with CI like that of [Gitlab CI/CD Pipelines](https://about.gitlab.com/features/gitlab-ci-cd/), it's a good way of building vulnerability-free container images.
