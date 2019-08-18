---
title: Setting up a secure Docker image scanning solution with Anchore and Drone CI
author: Sathya
type: post
date: 2019-03-12T06:16:24+00:00
url: /2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/
categories:
  - "Tips &amp; How-To's"
tags:
  - Anchore
  - container security
  - containers
  - Docker

---
A while back I had done a round up of a few <a rel="noopener noreferrer" href="https://sathyasays.com/2018/09/02/on-securing-containers-and-open-source-tools-for-scanning-vulnerabilities-in-docker-images/" target="_blank">container scanning solutions</a> and had mentioned I wanted to take another look at Anchore. The past few days, I&#8217;ve been playing a bit with Anchore &#8211; this time, integrating it with <a rel="noopener noreferrer" href="https://drone.io/" target="_blank">Drone CI</a>.

Drone is a &#8220;Container-Native, Continuous Delivery Platform&#8221; built using Go. It makes use of a YAML file, .drone.yml to define and execute the pipeline.

### End Goal

For this project, we will be integrating Drone and Anchore. With the setup complete, every push to the remote repository will trigger the Docker image to be built. The built Docker image will then be added to Anchore Engine for analysis and scanning. Drone integrates with most popular SCM tools &#8211; and for this project, we will integrate with Github.

### Setting up Drone

<a href="https://docs.drone.io/installation/github/" target="_blank" rel="noopener noreferrer">Follow the instructions</a> listed on Drone&#8217;s Installation Guide to set up Drone. A sample Drone server configuration and the command to start Drone is listed below. Make sure to substitute the client id and secret with the one generated from the setup<figure class="wp-block-embed">

<div class="wp-block-embed__wrapper">
  <div class="gist-oembed" data-gist="2f6b628135586d030b6f3405d2ab8d3b.json">
  </div>
</div></figure> 

Run Drone with the following command<figure class="wp-block-embed">

<div class="wp-block-embed__wrapper">
  <div class="gist-oembed" data-gist="661b02a1c7d5b0bebc6e1c1ab1a567d0.json">
  </div>
</div></figure> 

Once Drone server is up and running, head over to the Drone UI and click on &#8220;Activate&#8221; on the repo which you wish to integrate Drone with. Clicking on &#8220;Activate&#8221; sets up a Webhook on the repo so any activity against the repo results in an event being generated and the event is then pushed to Drone.

### Setting up Anchore Engine

Follow the instructions on Anchore&#8217;s <a href="https://anchore.freshdesk.com/support/solutions/articles/36000020729-install-with-docker-compose" target="_blank" rel="noopener noreferrer">website to install and run Anchore</a>. Once Anchore is up and running, we can use anchore-cli&nbsp;to interact with the image. Specifically, to scan the image, we need to:

  * Submit the image to Anchore Engine for analysis
  * Wait till the Analysis Engine is complete
  * Evaluate the analysis against the policy engine

We can achieve this by the following sequence of commands

<pre class="wp-block-preformatted">anchore-cli image add &lt;image name&gt;
anchore-cli image wait &lt;image name&gt;
anchore-cli evaluate check &lt;image name&gt;</pre>

Combining these commands with Drone&#8217;s pipeline we get this for the<a rel="noopener noreferrer" href="https://github.com/sathya-demo/subreddit-fetcher/blob/83fe5d0d31d4e225202d7d8694a8885ba818e57d/.drone.yml" target="_blank">.drone.yml file</a><figure class="wp-block-embed">

<div class="wp-block-embed__wrapper">
  <div class="gist-oembed" data-gist="0412331d117026807e34a647fa148998.json">
  </div>
</div></figure> 

Commit the .drone.yml file and push the changes to the repository. This results in the commit and push event being delivered to Drone, kickstarting the Drone pipeline.

Navigating to the Drone UI will show the pipeline stages and result of each pipeline stage. An example screenshot is shown below

<div class="wp-block-image">
  <figure class="aligncenter"><img data-attachment-id="1737" data-permalink="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/drone-pipeline-ui/" data-orig-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?fit=2142%2C1274&ssl=1" data-orig-size="2142,1274" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="Drone Pipeline UI" data-image-description="" data-medium-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?fit=608%2C362&ssl=1" data-large-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?fit=740%2C440&ssl=1" src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?resize=608%2C362&#038;ssl=1" alt="Drone Pipeline UI" class="wp-image-1737" srcset="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?resize=608%2C362&ssl=1 608w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?resize=768%2C457&ssl=1 768w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?resize=800%2C476&ssl=1 800w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?resize=840%2C500&ssl=1 840w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-pipeline-UI-.png?w=1480&ssl=1 1480w" sizes="(max-width: 608px) 100vw, 608px" data-recalc-dims="1" /></figure>
</div>

Comparing against the .drone.yml file, you can see that Drone created a new pipeline(boringly titled &#8220;default&#8221; consisting of 5 stages:

  * clone stage for cloning the repo. Although this isn&#8217;t listed in the .drone.yml file, Drone by default supports git and automatically adds the clone stage as the first stage
  * Build stage for building the Docker image and tagging it with the SHA of the commit.
  * Analyze stage for submitting the built Docker image to Anchore for image and vulnerability analysis
  * Policy Check stage for evaluating the Docker image and validating whether the image is good to deploy or not. In my earlier post I&#8217;d mentioned that creating and editing policies is a pain &#8211; but recently, Anchore has released a <a href="https://anchore.com/blog/introducing-anchore-policy-hub/" target="_blank" rel="noopener noreferrer">centralized repository of policies</a> that can be downloaded and installed.

If the policy check (or any stage) fails, the pipeline ends and does not trigger subsequent stages.

<div class="wp-block-image">
  <figure class="aligncenter"><img data-attachment-id="1738" data-permalink="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/drone-failed-policy-evaluation/" data-orig-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?fit=2122%2C1054&ssl=1" data-orig-size="2122,1054" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="Drone Failed Policy evaluation" data-image-description="" data-medium-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?fit=608%2C302&ssl=1" data-large-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?fit=740%2C367&ssl=1" src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation-608x302.png?resize=608%2C302&#038;ssl=1" alt="" class="wp-image-1738" srcset="https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?resize=608%2C302&ssl=1 608w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?resize=768%2C381&ssl=1 768w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?resize=800%2C397&ssl=1 800w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?resize=840%2C417&ssl=1 840w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2019/03/drone-failed-policy-evaluation.png?w=1480&ssl=1 1480w" sizes="(max-width: 608px) 100vw, 608px" data-recalc-dims="1" /></figure>
</div>

You can extend the pipeline further, adding steps to retag the Docker Image and push it to <a href="https://aws.amazon.com/ecr/" target="_blank" rel="noopener noreferrer">Amazon Elastic Container Registry (ECR)</a> &#8211; and Drone with its <a href="http://plugins.drone.io/drone-plugins/drone-ecr/" target="_blank" rel="noopener noreferrer">ECR plugin</a> makes it very easy to do so.

What Next?

You can take a look at Drone&#8217;s <a href="https://docs.drone.io/user-guide/pipeline/conditions/" target="_blank" rel="noopener noreferrer">Conditions</a> and <a href="https://docs.drone.io/user-guide/pipeline/triggers/" target="_blank" rel="noopener noreferrer">Triggers</a> which lets you define and limit pipeline execution based on specific events/branches. Combined with writing your plugins, Drone can let you set up a complete, secure CI/CD platform for your Docker images.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1724" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1724" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1724" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>