---
title: Scanning Docker Image for Vulnerabilities with Aqua MicroScanner
author: Sathya
type: post
date: 2018-05-28T18:10:16+00:00
url: /2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/
categories:
  - "Tips &amp; How-To's"
tags:
  - Aqua
  - Clair
  - containers
  - Docker
  - Twistlock
  - vulnerability
  - vulnerability scanner

---
Containers are slowly becoming the standardized units of deployment. As containers become more popular, they also become the focus targets for attacking the system via vulnerabilities present in the packages within the image. There are quite a few container vulnerability scanning solutions (example: <a href="https://github.com/coreos/clair" target="_blank" rel="noopener">Clair</a>, <a href="https://www.twistlock.com" target="_blank" rel="noopener">Twistlock</a>, <a href="https://www.aquasec.com" target="_blank" rel="noopener">Aqua</a>) &#8211; however most of them are either commercial or require an elaborate setup, which makes it difficult for individual developers to involve them as part of the container build process.

<!--more-->

I found recently that Aqua has introduced a free-to-use tool called <a href="https://github.com/aquasecurity/microscanner" target="_blank" rel="noopener">Aqua MicroScanner</a> for scanning container images for package vulnerabilities. What makes this even more attractive and easy-to-use is that it doesn&#8217;t need any elaborate or predefined server setups &#8211; and all that is needed to use this is:

  * Get a token from Aqua
  * Add the scanner and run it as part of the container build process

If the image contains any packages with vulnerabilities, Aqua will present a summary of the vulnerabilities, the average CVE score as well as a list of the found vulnerabilities.

To get started with Aqua MicroScanner, register for a token

    $ docker run --rm -it aquasec/microscanner --register <email address>

With the token available, add it as part of your build process. For example, if we were to check and scan an image based on nginx, the Dockerfile would look like below

`<br />
FROM nginx:1-alpine<br />
RUN apk add --no-cache ca-certificates && update-ca-certificates<br />
ADD https://get.aquasec.com/microscanner .<br />
RUN chmod +x microscanner<br />
RUN ./microscanner <token><br />
` 
  
When we build the container with

`$ docker build .`

The scanner will be executed and will scan the Docker image. The vulnerability found will be displayed as below
  
`"vulnerabilities": [<br />
{<br />
"name": "CVE-2016-3189",<br />
"description": "Use-after-free vulnerability in bzip2recover in bzip2 1.0.6 allows remote attackers to cause<br />
a denial of service (crash) via a crafted bzip2 file, related to block ends set to before the start of the block.",<br />
"nvd_score": 4.3,<br />
"nvd_score_version": "CVSS v2",<br />
"nvd_vectors": "AV:N/AC:M/Au:N/C:N/I:N/A:P",<br />
"nvd_severity": "medium",<br />
"nvd_url": "https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2016-3189",<br />
"vendor_score": 4.3,<br />
"vendor_score_version": "CVSS v2",<br />
"vendor_vectors": "AV:N/AC:M/Au:N/C:N/I:N/A:P",<br />
"vendor_severity": "medium",<br />
"publish_date": "2016-06-30",<br />
"modification_date": "2017-08-21"<br />
}<br />
]<br />
` 
  
The summary would be like so:

`"vulnerability_summary": {<br />
"total": 2,<br />
"medium": 2,<br />
"score_average": 4.3,<br />
"max_score": 4.3<br />
}<br />
` 

Aqua will stop the build if it finds any vulnerabilities of severity &#8220;High&#8221; &#8211; however, we can pass  `--continue-on-failure` flag to ignore the High severity issues and continue the build.

I think this tool is really good, especially for small developers &#8211; with just few lines of Dockerfile instructions, the developer is able add vulnerability scanning of the images &#8211; and combined with CI like that of <a href="https://about.gitlab.com/features/gitlab-ci-cd/" target="_blank" rel="noopener">Gitlab CI/CD Pipelines</a>, it&#8217;s a good way of building vulnerability-free container images.

&nbsp;

PS: I will be speaking about Container Security at <a href="http://konfhub.com/cloudnativemeetup.html" target="_blank" rel="noopener">Cloud Native Meetup: Containers & Serverless Deepdive</a>. Do join if interested!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1600" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1600" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1600" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2018/05/28/scanning-docker-image-for-vulnerabilities-with-aqua-microscanner/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>