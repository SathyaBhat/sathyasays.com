---
title: Taking on the DigitalOcean Kubernetes Challenge - GitOps CI/CD with Argo CD and Tekton
author: Sathyajith Bhat
type: post
date: 2021-12-30T10:00:00+00:00
url: /2021/12/30/digitalocean-kubernetes-challenge-gitops-argo-tekton
summary: I attempt to complete the DigitalOcean Kubernetes Challenge and deploy a GitOps CI/CD solution using Tekton and Argo CD
featureimage: https://i.sathyabh.at/ss/dok8s/argo.png
meta_image: https://i.sathyabh.at/ss/dok8s/argo.png
categories:
  - DevOps
tags:
  - Kubernetes
  - Terraform
  - Docker
---
I came across DigitalOcean's Kubernetes challenge a few weeks back and found it to be interesting. The [Kubernetes Challenge](https://www.digitalocean.com/community/pages/kubernetes-challenge) is an event to pick up a challenge from the list provided by DigitalOcean and complete them. The challenge involves creating, configuring, and deploying apps to a [DigitalOcean Managed Kubernetes cluster](https://www.digitalocean.com/products/kubernetes/). I've been looking at improving my Kubernetes skills well beyond the "deploy a StatefulSet and you're done" level, so I looked at the available challenges. 

DigitalOcean did a wonderful job of coming up with a list of challenges aimed at people who're just getting started, all the way to those who are familiar and yet still need something to improve their skills. To make things even better, DigitalOcean also provided some credits ($60 for the beginner challenge, $120 for the advanced and expert challenges) to those who were doing the challenge. Thanks to DigitalOcean for the credits which made doing this challenge without us having to spend anything.

This might be a bit of a lengthy read. I would encourage you to use the table of contents on the right side to jump to specific parts that you may be interested in.

## The Challenges 

I don't know how long the page would be up, so I am documenting the tasks for my reference for the future so I can pick these up:

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

  GitOps is today the way you automate deployment pipelines within Kubernetes itself, and Argo CD  is currently one of the leading implementations. Install it to create a CI/CD solution, using tekton and kaniko for actual image building. https://medium.com/dzerolabs/using-tekton-and-argocd-to-set-up-a-kubernetes-native-build-release-pipeline-cf4f4d9972b0
- **Deploy a solution for policy enforcement**

  Install and use Kyverno, a policy engine designed for Kubernetes. It can validate, mutate, and generate configurations using admission controls and background scans. Kyverno policies are Kubernetes resources and do not require learning a new language. Kyverno is designed to work well with tools you already use like kubectl, kustomize, and Git. Create policies for mandatory labels for every deployment, and image download only permitted from DOCR.  https://kyverno.io/policies/
- **Deploy a solution for configuring Kubernetes "from the inside"**

  Install Crossplane, which is like Terraform but you manage the infra from inside Kubernetes, not from outside. Crossplane is an open source Kubernetes add-on that enables platform teams to assemble infrastructure from multiple vendors, and expose higher level self-service APIs for application teams to consume, without having to write any code.


Since I wanted to challenge myself, I picked up a challenge from the Expert category. Specifically, I picked up GitOps CI/CD implementation using Tekton pipelines, Kaniko for building containers, and Argo CD for continuous delivery. I picked this up because I wanted to understand Argo better, as we're looking to use this at work soon. 

I had some personal goals too:

* Use Infrastructure as Code (IaC) for everything - from setting up the Kubernetes cluster to deploying the Kubernetes manifests
* No manual setup for any component
* Use the entire Argo stack ([Argo CD](https://argo-cd.readthedocs.io/en/stable/) + [Argo Events](https://argoproj.github.io/argo-events/) + [Argo Workflows](https://argoproj.github.io/argo-workflows/)).

Time was also a factor since I had picked up the challenge only in the last week of December, meaning that I had about a week to learn, understand, set up everything, and finish this write up (I could have cheesed with just a readme link, but wanted to document). I knew that I may have bitten more than I could chew, especially having to set up tenet #1, ie infrastructure as code for *everything*, including Kubernetes manifests using the Helm & Kubernetes provider for Terraform which I had never looked at before, but I wanted to try it out, anyway. 

## The Results

So did I complete the challenge? Well, yes, and no - I ended up spending a lot more time than I intended in wrestling with Terraform, especially the Kubernetes & Helm provider for Helm and in trying to get the IaC for the manifests and getting Kubernetes auth to work correctly. Given that I was running out of time, I had to compromise on my tenets and personal goals and skipped the full Argo stack and use the Tekton & Argo CD flow. I wasn't familiar with Argo & Tekton either, but DigitalOcean had linked to this great write-up by [Adri Villela of D0 Labs](https://medium.com/dzerolabs/using-tekton-and-argocd-to-set-up-a-kubernetes-native-build-release-pipeline-cf4f4d9972b0) which made it a lot easier and faster to setup. 

I ran into some more challenges getting Kaniko to authenticate to Docker Hub to push the image. Adri was kind enough to provide example repos for the entire setup of the Tekton Pipelines and a sample application but needed some changes for them to work correctly in deploying the changes. 

In the end, thanks to Adri, Kubernetes documents, and a lot of fiddling around, I have the entire setup ready!

* A Managed DigitalOcean Kubernetes cluster created from Terraform
* Tekton Pipelines for building the application Docker image and pushing it to Docker Hub
* Argo CD for deploying the changes to the Kubernetes cluster

There are three repositories:

* A repo for setting up the infrastructure and software stack (Argo, Ambassador, Tekton) - [link to the repo](https://github.com/SathyaBhat/dok8s-gitops)
  
* A repo for setting up the Tekton pipelines - [link to the pipeline repo](https://github.com/SathyaBhat/tekton-pipeline-example-pipeline)
* A repo for the actual app - [link to the app repo](https://github.com/SathyaBhat/tekton-pipeline-example-pipeline)

Argo CD is configured to look at both the pipeline and the application repos. When a change is pushed to the pipeline repo, Argo CD will determine that the repo is out of sync with what is deployed in the Kubernetes cluster. 

Argo CD also has an option to enable automatic sync. Enabling automatic results in Argo automatically determining when an application is out of sync and will automatically sync. This results in the pipeline repo changes being automatically deployed by Argo CD sync when a change is pushed to the main branch.

In the case of the application, a Tekton Event Listener is listening to a WebHook defined on the GitHub repo. this Event Listener will trigger a Tekton Pipeline run that will build the Docker Image and deploy it to the destination, resulting in automated deploys upon merge to the main branch.

Let's see how the Argo CD UI looks like post-deploy:

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-pipeline.png" "The Tekton Pipeline setup with Argo CD" "GitOps with Kubernetes and Argo CD " >}}

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-app-deploy-start.png" "Argo CD starting deploy of the app" "GitOps with Kubernetes and Argo CD " >}}

{{< fancybox "https://i.sathyabh.at/ss/dok8s" "argo-app-deploy.png" "Argo CD finishing deploy of the app with the new pod coming healthy" "GitOps with Kubernetes and Argo CD" >}}

## Setting up the Kubernetes Cluster 

The first step was to deploy the Kubernetes cluster. As required by the challenge, I used DigitalOcean's managed Kubernetes cluster and used Terraform to deploy it. Using the DigitalOcean provider, the Terraform code to create the cluster was quite straightforward as shown in [below](https://github.com/SathyaBhat/dok8s-gitops/blob/main/infra/k8s.tf#L1-L13)

```hcl
resource "digitalocean_kubernetes_cluster" "dok8s" {
  ha      = false
  name    = "dok8s"
  region  = "ams3"
  version = "1.21.5-do.0"
  node_pool {
    auto_scale = true
    min_nodes  = 1
    max_nodes  = 5
    name       = "k8s-workers"
    size       = "s-2vcpu-4gb" #  from https://slugs.do-api.dev/ 
  }
}
```

With the managed K8s offering, DigitalOcean does the heavy lifting of managing the control plane, leaving us only to focus on running our applications. Deploying the cluster was reasonably fast and accurate - on average, the Terraform apply time to create the cluster was about 6 minutes. With this fast turnaround time, I didn't feel necessary to keep the cluster running when I was not using it and would frequently tear it down and bring it up as I was working on it. Kudos to the DigitalOcean Kubernetes team for making this such a simple and fast experience! A nice bonus was that the Kubernetes dashboard was also available out of the box, without the need to deploy it using additional steps. 

Since this challenge was all about learning new things, I took this time to explore Terraform cloud to manage remote states and workspaces. Terraform cloud was a good experience, but one gotcha that tripped me was that using Terraform cloud and Workspace enables execution mode as remote by default - this means that Terraform plans and applies happen remotely on Terraform's cloud infrastructure and the Terraform CLI is a remote log streamer. This means that any environment or Terraform variables will need to be set in the Terraform workspaces on the Terraform Cloud portal, else the Terraform run fails. 

The original goal was to deploy Argo and other assorted components via Terraform as well. However, due to lack of time, I skipped this and created the resources via `kubectl apply` commands in the following order:

```bash 

## Install Ambassador -- A Kubernetes-native API Gateway built on Envoy, that also acts as Ingress
kubectl apply -f https://www.getambassador.io/yaml/aes-crds.yaml && kubectl wait --for condition=established --timeout=90s crd -lproduct=aes && kubectl apply -f https://www.getambassador.io/yaml/aes.yaml && kubectl -n ambassador wait --for condition=available --timeout=90s deploy -lproduct=aes

## Install Cert Manager to handle TLS certificate provisioning and management 
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.0.0/cert-manager.crds.yaml
helm repo add jetstack https://charts.jetstack.io && helm repo update
kubectl create ns cert-manager
helm install cert-manager --namespace cert-manager jetstack/cert-manager

## Get the LoadBalancer IP fronted by Ambassador

kubectl get -n ambassador service ambassador -o "go-template={{range .status.loadBalancer.ingress}}{{or .ip .hostname}}{{end}}"

## Did manually - add this IP as an A record to a domain/subdomain in your DNS control panel

## Configure TLS for Ambassador and point to the domain created above 
kubectl apply -f apps/manifests/ambassador-tls.yaml
kubectl apply -f apps/manifests/ambassador-service.yaml


## Create Argo CD namespace
kubectl create namespace argocd

## Install Argo CD CRDs
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v1.7.6/manifests/install.yaml

## Point /argo-cd path on the domain to Argo CD via Ambassador

kubectl apply -f apps/manifests/argocd-ambassador.yaml

## Install Tekton pipelines & triggers CRDs

kubectl apply -f https://storage.googleapis.com/tekton-releases/pipeline/previous/v0.16.0/release.yaml
kubectl apply -f https://storage.googleapis.com/tekton-releases/triggers/previous/v0.8.1/release.yaml

## Did manually - create a Github Personal Access token for Argo CD to talk to GitHub

## Did manually - reset Argo CD admin password

## Add our repos to Argo CD 

argocd repo add https://github.com/SathyaBhat/tekton-pipeline-example-app --username $SCM_USERNAME --password $SCM_PAT
argocd repo add https://github.com/SathyaBhat/tekton-pipeline-example-pipeline --username $SCM_USERNAME --password $SCM_PAT


## Create apps in Argo CD for it to monitor and deploy 

argocd app create tekton-pipeline-app --repo https://github.com/SathyaBhat/tekton-pipeline-example-pipeline --path tekton-pipeline --dest-server https://kubernetes.default.svc --dest-namespace tekton-argocd-example
argocd app create 2048-game-app --repo https://github.com/SathyaBhat/tekton-pipeline-example-app --path kustomize --dest-server https://kubernetes.default.svc --dest-namespace game-2048 --sync-option CreateNamespace=true

## Deploy the pipeline

argocd app sync tekton-pipeline-app --prune
```

For the full script and a detailed description of the steps, I would highly recommend you to read Adri Villela's posts on [Installing Ambassador, Argo CD, and Tekton on Kubernetes](https://medium.com/dzerolabs/installing-ambassador-argocd-and-tekton-on-kubernetes-540aacc983b9) and [Kubernetes-Native Build & Release Pipelines with Tekton and Argo CD](https://medium.com/dzerolabs/using-tekton-and-argocd-to-set-up-a-kubernetes-native-build-release-pipeline-cf4f4d9972b0). These posts will have an in-depth explanation of each of the steps and how to do the manual steps. The script and the code that is used is available in this [GitHub repo](https://github.com/SathyaBhat/dok8s-gitops).

With all these, the GitOps pipeline is ready!

## Things that I learned, and what I got stuck on

As with most new tech, some things were quite simple, and some others were a lot harder than I initially thought they would. I wanted to understand each step before applying it, so I had to skip my original goal of full Argo stack due to time constraints. Here are other additional things that tripped me and spent multiple hours on trying to get resolved:

* When Terraform does a remote plan & apply, it seems to ignore locally specified (even if from the CLI) Terraform variables/environment variables - took a while to realize I had to set these in Terraform Cloud portal.
* I wanted to keep the infra and apps deployment separate, and for the apps deploy, I had to fetch cluster certificate, token, and endpoint. The initial goal was to export these as output in the infra module and use the remote state data source to save them to variables. For whatever reasons, this approach wasn't working and the Cluster CA details was not set correctly, leading to a misleading 
  > x509: certificate signed by unknown authority
  error. I suspect this is because of some weird interaction with the way Terraform marks secrets as sensitive and the Kubernetes provider tries to deserialize this. As a workaround, I exported the cluster name and then used the `digitalocean_kubernetes_cluster` data source to fetch these secrets. You can see the way I originally tried it ([infra](https://github.com/SathyaBhat/dok8s-gitops/blob/cf502260ea2726f66c3f292bc21e8fa78c903658/infra/outputs.tf#L6-L20), [apps](https://github.com/SathyaBhat/dok8s-gitops/blob/cf502260ea2726f66c3f292bc21e8fa78c903658/apps/providers.tf#L24-L36)) and my final approach ([infra](https://github.com/SathyaBhat/dok8s-gitops/blob/213c01cee87a8d502d7c21d35eb8322579b8677f/infra/outputs.tf#L10-L12), [apps](https://github.com/SathyaBhat/dok8s-gitops/blob/213c01cee87a8d502d7c21d35eb8322579b8677f/apps/providers.tf#L27-L47))
* Another thing I got stuck on for a long time: for whatever reasons, Kaniko kept rejecting the Docker Hub credentials and kept throwing error 
  > error checking push permissions -- make sure you entered the correct tag name, and that you are authenticated correctly, and try again
  It seems Kaniko wasn't able to pick up `kubernetes.io/basic-auth` secret type, and after changing this to `kubernetes.io/dockerconfigjson` secret type, Kaniko picked up the credentials and could build and push the image to Docker Hub correctly. You can find [my commit](https://github.com/SathyaBhat/tekton-pipeline-example-pipeline/commit/8d55240c5d54aa7cf83dbed98df9b05bac059f50) that fixes this in my repo.

## Conclusions and Future Plans

I had a lot of fun and some frustration in completing this challenge. I picked some new skills and learned about:

- Terraform Cloud
- Kubernetes, DigitalOcean and Helm providers for Terraform
- Kustomize & Kustomization
- Ambassador 
- Tekton Pipelines, Tasks
- Argo applications

As I completed this. The credits from DigitalOcean should last till the end of this Jan, so I hope to:

* Replace Ambassador with something else (or maybe keep Ambassador, it looks quite easy to do the mappings)
* Understand Kaniko deeper
* Add the full Argo stack
* (as a stretch goal) Move all the kubectl apply to Terraform code (or maybe even [cdktf](https://learn.hashicorp.com/tutorials/terraform/cdktf)).

Subscribe [to the feed](https://sathyasays.com/index.xml) to be notified of new posts!
