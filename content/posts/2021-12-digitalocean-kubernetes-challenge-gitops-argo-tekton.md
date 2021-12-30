---
title: Taking on the DigitalOcean Kubernetes Challenge - GitOps with Argo and Tekton
author: Sathyajith Bhat
type: post
date: 2021-12-30T10:00:00+00:00
url: /2021/12/20/digitalocean-kubernetes-challenge-gitops-argo-tekton
description: I attempt to complete teh DigitalOcean Kubernetes Challenge
featured_image: https://i.sathyabh.at/sb/dok8s/argo.png
categories:
  - DevOps
tags:
  - Kubernetes
  - Docker
---
I came across DigitalOcean's Kubernetes challenge few weeks back, and found it to be interesting. The [Kubernetes Challenge](https://www.digitalocean.com/community/pages/kubernetes-challenge) is an event to pick up a challenge from the list provided by DigitalOcean and complete them. The challenge involves creating, configuring and deploying apps to a DigitalOcean Managed Kubernetes cluster. I've been looking at improving my Kubernetes skills well beyond the "deploy a statefulset and you're done" kind of tasks, so I took a look at the tasks. DigitalOcean did a wonderful job of coming up with a list of tasks aimed at people who're just getting started, all the way to those who are familiar and yet still need something to improve their skills. To make things even better, DigitalOcean also provided some credits ($60 for the beginner challenge, $120 for the advanced and expert challenges) to those who were doing the challenge. Thanks to DigitalOcean for the credits which made doing this challenge a lot more easy without us having to spend anything.

## The Challenges 

I don't know how long the page would be up, so I am documenting the tasks for my reference for future so I can pick these up (and maybe livestream doing these):

### New to Kubernetes

- **Deploy an internal container registry**

  Kubernetes does not provide an internal container registry but it is often useful to add one. There are many projects which enable you to deploy an internal container registry, such as Harbour or Trow.
- **Deploy a log monitoring system**

  So your applications produce logs. Lots of logs. How are you supposed to analyze them? A common solution is to aggregate and analyze them using the ELK stack, alongside fluentd or fluentbit.
- **Deploy a scalable SQL database cluster**

  When deploying a database on Kubernetes, you have to make it redundant and scalable. You can rely on database management operators like KubeDB or database-specific solutions like Kubegres for PostgreSQL or the MySQL Operator for MySQL. 
- **Deploy scalable NoSQL database cluster**

  When it comes to cloud native, using No-SQL solutions has its advantages. You can deploy a cluster of MongoDB, Cassandra, or CouchDB instances to explore how to run a NoSQL database in Kubernetes. 

### Used Kubernetes before

- **Deploy a scalable message queue**

  A critical component of all the scalable architectures are message queues used to store and distribute messages to multiple parties and introduce buffering. Kafka is widely used in this space and there are multiple operators like Strimzi or to deploy it. For this project, use a sample app to demonstrate how your message queue works. 
- **Deploy a big data management system**

  Big data systems live in clouds as they need to be scalable. One of the more used big data management solutions is Spark, and it can be installed in Kubernetes leveraging its native integration with Kubernetes. 
- **Deploy a machine learning management platform**

  Machine learning requires complex workflows, and can benefit from an AI/ML management platform. Kubeflow offers a wide range of features in this area, including creation of Notebooks, Pipelines, Model training, Model Serving, and more.
- **Deploy a security and compliance system**

  When you deploy an image you may also deploy a security threat, and images can become quickly insecure as new threats are discovered and disclosed. To continuously monitor and detect threats, you can deploy a tool like Falco.

### Kubernetes expert

- **Deploy a virtual cluster solution**

  Install vcluster to test upgrades (eg. 1.20 to 1.21 DOKS version) of your cluster. With a virtual cluster, you can create a new Kubernetes cluster inside your existing DOKS cluster, test the application in this new vcluster, and then upgrade your original cluster if everything works well with the new version.   https://loft-sh.medium.com/high-velocity-engineering-with-virtual-kubernetes-clusters-7df929ac6d0a
- **Deploy a GitOps CI/CD implementation**

  GitOps is today the way you automate deployment pipelines within Kubernetes itself, and ArgoCD  is currently one of the leading implementations. Install it to create a CI/CD solution, using tekton and kaniko for actual image building. https://medium.com/dzerolabs/using-tekton-and-argocd-to-set-up-a-kubernetes-native-build-release-pipeline-cf4f4d9972b0
- **Deploy a solution for policy enforcement**

  Install and use Kyverno, a policy engine designed for Kubernetes. It can validate, mutate, and generate configurations using admission controls and background scans. Kyverno policies are Kubernetes resources and do not require learning a new language. Kyverno is designed to work well with tools you already use like kubectl, kustomize, and Git. Create policies for mandatory labels for every deployment, and image download only permitted from DOCR.  https://kyverno.io/policies/
- **Deploy a solution for configuring Kubernetes "from the inside"**

  Install Crossplane, which is like Terraform but you manage the infra from inside Kubernetes, not from outside. Crossplane is an open source Kubernetes add-on that enables platform teams to assemble infrastructure from multiple vendors, and expose higher level self-service APIs for application teams to consume, without having to write any code.


Since I wanted to challenge myself, I picked up a challenge from the Expert category. Specially, I picked up GitOps CI/CD implementation with using Tekton pipelines, Kaniko for building containers and ArgoCD for continuous delivery. I picked this up because I wanted to understand Argo better, as we're looking at using this at work in the near future. 

I had some personal goals too:

* Use Infrastructure as Code (IaC) for everything - from setting up the Kubernetes cluster to deploying the Manifests
* No manual setup for any component
* Use the entire Argo stack ([Argo CD](https://argo-cd.readthedocs.io/en/stable/) + [Argo Events](https://argoproj.github.io/argo-events/) + [Argo Workflows](https://argoproj.github.io/argo-workflows/)).

Time was also a factor since I had picked up the challenge only in the last week of December, meaning that I had about a week to learn, understand, setup everything and finish this write up(I could have cheesed with just a readme link, but wanted to document in detail). I knew that I may have bitten more than I could chew, especially having to setup tenet #1, ie infrastrucutre as code for *everything*, including the Helm & Kubernetes provider for Terraform which I had never looked at before, but I wanted try it out anyway. 

### The Results

So did I complete the challenge? Well, yes and no - I ended up spending a lot more time than I intended in wrestling with Terraform, especially the Kubernetes & Helm provider for Helm and in trying to get the IaC for the manifests, and getting Kubernetes auth to work correctly. Given that I was running out of time, I had to compromise on my tenets and personal goals and decided to skip the full Argo stack and use the Tekton & Argo CD flow. I wasn't familiar with Argo & Tekton either, but DigitalOcean had linked to this great write up by [Adri Villela of D0 Labs](https://medium.com/dzerolabs/using-tekton-and-argocd-to-set-up-a-kubernetes-native-build-release-pipeline-cf4f4d9972b0) which made it a lot easier and faster to setup. 

I ran into some more challenges getting Kaniko to authenticate to Docker Hub to push the image. Adri was kind enough to provide example repos for the entire setup of the Tekton Pipelines and an sample application, but needed couple of changes for them to work correctly in deploying the changes. 

In the end, thanks to Adri, Kubernetes documents and a lot of fiddling around, I have the entire setup ready!

* A Managed DigitalOcean Kubernetes cluster created from Terraform
* Tekton Pipelines for building the application Docker Image and pushing it to Docker Hub
* ArgoCD for deploying the changes to the Kubernetes cluster

In total, there are three repositories:

* A repo for setting up the Infrastructure and software stack (Argo, Amabassador, Tekton) - [link to the repo](https://github.com/SathyaBhat/dok8s-gitops)
  
* A repo for setting up the Tekton pipelines - [link to the pipeline repo](https://github.com/SathyaBhat/tekton-pipeline-example-pipeline)
* A repo for the actual app - [link to the app repo](https://github.com/SathyaBhat/tekton-pipeline-example-pipeline)

ArgoCD is configured to look at both the pipeline as well as the application repos. When a change is pushed to the pipeline repo, ArgoCD will determine that the repo is out of sync with what is deployed in the Kubernetes cluster. 

ArgoCD also has an option to enable automatic sync. Enabling automatic results in Argo automatically determining when an application is out of sync and will automatically sync. This results in the pipeline repo changes being automatically deployed by ArgoCD sync when a change is pushed to the main branch.

In case of the application, there's a tekton Event Listener listening to a WebHook defined on the GitHub repo. this Event Listener will trigger a Tekton Pipeline run that will build the Docker Image and deploy it to the destination, resulted in automated deploys upon merge to the main branch.

Let's see how the Argo CD UI looks like post deploy:

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-pipeline.png" "The Tekton Pipeline setup with ArgoCD" "GitOps with Kubernetes and ArgoCD " >}}

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-app-deploy-start.png" "ArgoCD starting deploy of the app" "GitOps with Kubernetes and ArgoCD " >}}

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-app-deploy.png" "ArgoCD finishing deploy of the app with the new pod coming healthy" "GitOps with Kubernetes and ArgoCD " >}}


