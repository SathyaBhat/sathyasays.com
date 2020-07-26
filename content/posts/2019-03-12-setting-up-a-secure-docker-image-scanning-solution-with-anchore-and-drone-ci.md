---
title: Setting up a secure Docker image scanning solution with Anchore and Drone CI
author: Sathya
type: post
date: 2019-03-12T06:16:24+00:00
url: /2019/03/12/setting-up-a-secure-docker-image-scanning-solution-with-anchore-and-drone-ci/
categories:
  - "Tips & How-To's"
tags:
  - Anchore
  - container security
  - containers
  - Docker

---
A while back I had done a round up of a few [container scanning solutions](https://sathyasays.com/2018/09/02/on-securing-containers-and-open-source-tools-for-scanning-vulnerabilities-in-docker-images/) and had mentioned I wanted to take another look at Anchore. The past few days, I've been playing a bit with Anchore - this time, integrating it with [Drone CI](https://drone.io/).

Drone is a "Container-Native, Continuous Delivery Platform" built using Go. It makes use of a YAML file, .drone.yml to define and execute the pipeline.

### End Goal

For this project, we will be integrating Drone and Anchore. With the setup complete, every push to the remote repository will trigger the Docker image to be built. The built Docker image will then be added to Anchore Engine for analysis and scanning. Drone integrates with most popular SCM tools - and for this project, we will integrate with Github.

### Setting up Drone

[Follow](https://docs.drone.io/installation/github/) the instruction listed on Drone's Installation Guide to set up Drone. A sample Drone server configuration and the command to start Drone is listed below. Make sure to substitute the client id and secret with the one generated from the setup

{{< gist SathyaBhat 2f6b628135586d030b6f3405d2ab8d3b >}}


Run Drone with the following command

{{< gist SathyaBhat 661b02a1c7d5b0bebc6e1c1ab1a567d0 >}}

Once Drone server is up and running, head over to the Drone UI and click on "Activate" on the repo which you wish to integrate Drone with. Clicking on "Activate" sets up a Webhook on the repo so any activity against the repo results in an event being generated and the event is then pushed to Drone.

### Setting up Anchore Engine

Follow the instructions on Anchore's [website to install and run Anchore](https://docs.anchore.com/current/docs/engine/quickstart/#step-1-download-the-docker-composeyaml-file-and-start). Once Anchore is up and running, we can use anchore-cli&nbsp;to interact with the image. Specifically, to scan the image, we need to:

  * Submit the image to Anchore Engine for analysis
  * Wait till the Analysis Engine is complete
  * Evaluate the analysis against the policy engine

We can achieve this by the following sequence of commands

{{< highlight bash >}}
anchore-cli image add <image name>
anchore-cli image wait <image name>
anchore-cli evaluate check <image name>
{{< /highlight >}}

Combining these commands with Drone's pipeline we get this for the [`.drone.yml file`](https://github.com/sathya-demo/subreddit-fetcher/blob/83fe5d0d31d4e225202d7d8694a8885ba818e57d/.drone.yml)

{{< gist SathyaBhat 0412331d117026807e34a647fa148998 >}}


Commit the .drone.yml file and push the changes to the repository. This results in the commit and push event being delivered to Drone, kickstarting the Drone pipeline.

Navigating to the Drone UI will show the pipeline stages and result of each pipeline stage. An example screenshot is shown below


{{< figure src="https://images.sbhat.me/ss/2019/03/drone-pipeline-UI--840x500.png" title="Drone Pipeline UI" >}}

Comparing against the `.drone.yml` file, you can see that Drone created a new pipeline(boringly titled "default" consisting of 5 stages:

  * clone stage for cloning the repo. Although this isn't listed in the .drone.yml file, Drone by default supports git and automatically adds the clone stage as the first stage
  * Build stage for building the Docker image and tagging it with the SHA of the commit.
  * Analyze stage for submitting the built Docker image to Anchore for image and vulnerability analysis
  * Policy Check stage for evaluating the Docker image and validating whether the image is good to deploy or not. In my earlier post I'd mentioned that creating and editing policies is a pain - but recently, Anchore has released a [centralized repository of policies](https://anchore.com/blog/introducing-anchore-policy-hub/) that can be downloaded and installed.

If the policy check (or any stage) fails, the pipeline ends and does not trigger subsequent stages.

<div class="wp-block-image">
  <figure class="aligncenter"><img src="https://images.sbhat.me/ss/2019/03/drone-failed-policy-evaluation-608x302.png" alt="" class="wp-image-1738" srcset="https://images.sbhat.me/ss/2019/03/drone-failed-policy-evaluation-608x302.png 608w, https://images.sbhat.me/ss/2019/03/drone-failed-policy-evaluation-768x381.png 768w, https://images.sbhat.me/ss/2019/03/drone-failed-policy-evaluation-800x397.png 800w, https://images.sbhat.me/ss/2019/03/drone-failed-policy-evaluation-840x417.png 840w" sizes="(max-width: 608px) 100vw, 608px" /></figure>
</div>

You can extend the pipeline further, adding steps to retag the Docker Image and push it to <a href="https://aws.amazon.com/ecr/" target="_blank" rel="noopener noreferrer">Amazon Elastic Container Registry (ECR)</a> - and Drone with its <a href="https://plugins.drone.io/drone-plugins/drone-ecr/" target="_blank" rel="noopener noreferrer">ECR plugin</a> makes it very easy to do so.

What Next?

You can take a look at Drone's <a href="https://docs.drone.io/user-guide/pipeline/conditions/" target="_blank" rel="noopener noreferrer">Conditions</a> and <a href="https://docs.drone.io/user-guide/pipeline/triggers/" target="_blank" rel="noopener noreferrer">Triggers</a> which lets you define and limit pipeline execution based on specific events/branches. Combined with writing your plugins, Drone can let you set up a complete, secure CI/CD platform for your Docker images.
