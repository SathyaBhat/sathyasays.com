---
title: Migrating my WordPress blogs to Hugo
author: Sathyajith Bhat
type: post
date: 2020-08-28T00:00:00+00:00
url: /2020/08/28/migrating-moving-your-wordpress-blog-to-hugo
categories:
  - "Tips & How-To's"
tags:
  - WordPress
  - Hugo
  - Migration

---

I started blogging with [WordPress about 13 years ago](https://sathyasays.com/2007/05/27/hello-world-2/). I had some free time since the joining date for my first job was about a month or so away. Armed with boredom, an Internet connection and an ample amount of free time, I started [Sathya Says](https://sathyasays.wordpress.com/) on WordPress.com hosting. Soon after, I came to know about domains, shared hosting and self-hosted WordPress and with my first ever salary, purchased [sathyasays.com](sathyasays.com), shared hosting and started writing about Linux experiences. The shared hosting served me quite well, enough to get tens of thousands of views per month(which surprised me quite a lot since I focused on Desktop Linux, a tiny niche). I experimented with AdSense and managed to hit the $100 threshold in about 4 months. I removed Adsense soon after, there was just no point with such abysmal CTRs. 

Fast forward a few years later, I was spending more time on keeping my WordPress install secure. The tipping point was when my DigitalOcean droplet was disconnected from their network as it was detected to be a contributor to a DDoS attack and it took DigitalOcean more than 2 days to re-enable networking so I can recover the data and fix it! I took this opportunity to disable WordPress and start exporting the data and import it into Hugo, to be hosted with [Netlify](https://www.netlify.com/). Here's how I went about exporting blogs.

### Hugo

Hugo is a static site generator. Unlike other systems like WordPress which dynamically builds a response page on visit, Hugo builds the pages when the content is created/updated. This doesn't mean you'll have to painstakingly build HTML for each page - Hugo provides a framework for building the pages. Your pages will be in the form of a Markdown file which stores the content of the posts. Hugo also supports Frontmatter which lets you keep the metadata of the page, within the page itself.  When you build a page in Hugo, it will parse through the Markdown file and generate a static HTML file. This static HTML can be hosted anywhere - from Amazon S3, Netlify etc. There's a lot of documentation on how to get started with but not a lot on how to migrate - so I thought I'll post on how I did the migration.

### So how do we export the data from WordPress?

Before starting the migration, I had two major goals:
- Data export from WordPress and import to Hugo should be done with as little work as possible
- There should be no broken links - in other words, the permalinks, tags, category links etc should not change

While WordPress comes with a Data export tool, its an XML dump of all the content and I'd have to spend a lot of time in importing it. The Tools page on Hugo's website listed some tools for working with WordPress XML backup but didn't try them out.

With these two goals in mind, I tried out decided to use SchumacherFM's [wordpress-to-hugo exporter](https://github.com/SchumacherFM/wordpress-to-hugo-exporter). The exporter is actually a WordPress plugin - and comes in two forms - as a CLI as well as a proper plugin that you can activate from the WordPress plugins page. I would recommend using the CLI approach - the data export is quite intensive and you might end up with a 504/Time out/failed export if the export doesn't get completed within the timeout settings.


### Step by step process

Below are the step-by-step process to export the data and import to Hugo

- Clone the `wordpress-to-hugo` exporter repo on the server where your WordPress instance is running, in the `wp-content/plugins` directory

      git clone https://github.com/SchumacherFM/wordpress-to-hugo-exporter.git
    
- Change to the `wordpress-to-hugo-exporter` directory within 

      cd wordpress-to-hugo-exporter

- Run the exporter 

      php hugo-export-cli.php

Depending on the size of your data and your server specifications, it might take anywhere from few seconds to a few minutes for the export to complete and will display the path where the file is saved.

    hugo-export-cli.php
    [INFO] tmp folder not found, use default. You could invoke php hugo-export-cli.php with an extra argument as the temporary folder path if needful.
    This is your file!
    /tmp/user/0/wp-hugo.zip

Download the file from the server using scp

    scp user@remotehost:/path/to/wp-hugo.zip .

The compressed file will contain your blog data - posts, pages, images with the metadata in a structure and the `config.yaml` file that Hugo expects. Just download a Hugo theme of your choice and update the config file accordingly. 


You can take a look at my blog repos for examples on structuring the directory:

- [Sathya Says](https://github.com/SathyaBhat/sathyasays.com)
- [My World](https://github.com/SathyaBhat/sathyabh.at)


### Some tips and points to note

While the export is almost seamless, there are some pointers before you start the export to get the cleanest export:

- Disable all your plugins, especially Jetpack. The plugins can often mess up the data exports with unnecessary cruft, making the Markdown exports bulkier than needed
- The `wordpress-to-hugo-exporter` keeps any HTML content within the page(for example any embedded content, image galleries etc) as inline HTML. This wasn't a problem earlier but as of [Hugo version 0.60](https://gohugo.io/news/0.60.0-relnotes/), the default Markdown rendering library by Hugo, Goldmark, no longer renders inline HTML out of the box and you will have to enable `unsafe` mode as below:

  config.yaml

      markup:
        goldmark:
          renderer:
            unsafe: true


  config.toml

      [markup]
        [markup.goldmark]
          [markup.goldmark.renderer]
            unsafe = true

  config.json

      {
        "markup": {
            "goldmark": {
              "renderer": {
                  "unsafe": true
              }
            }
        }
      }

  If you don't add these settings, the inline HTML would be omitted and replaced by this message

      <!-- raw HTML omitted -->

- With the plugin, special characters may be exported as HTML entities and may not be rendered correctly by Hugo, especially in tags.

### Hosting and Deploys

For hosting the imported blogs, I used [Netlify](https://www.netlify.com/). Netlify can connect [with your Github repo](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/) and deploy the changes the moment a commit has been pushed, making it quite easy to write, review, edit and rework on the posts if needed. [Netlify's deploy preview](https://docs.netlify.com/site-deploys/overview/#deploy-preview-controls) means that you can write a blog post, cut a Pull Request and Netlify will automatically publish a preview version - making editing and peer reviews easy, typically as comments on the Pull Request itself. Netlify's doing well as of now but have gradually started introducing more constraints and it is quite possible that Netlify might not be feasible in the near future, in which case I might just move the entire blog to GitHub pages, as described by Shantanu Goel in [his post here](https://shantanugoel.com/2020/01/05/migrate-hugo-blog-gitlab-s3-github-pages-actions/).

### Handling images

While using Git as the backend store for text was ideal, I wasn't happy with storing the blog images in the repo. I thought of using [Git LFS](https://git-lfs.github.com/) and Netlify Large Media uses this, I ultimately didn't end up using it since it's metered [under Netlify billing](https://www.netlify.com/pricing/#large-media) and Netlify's billing is not very granular. Ultimately I setup a Cloudfront CDN infront of an S3 bucket and started serving images off that. You can check [Bhuvana's blog post on how to do this](https://dev.to/aws-heroes/self-hosting-secured-static-web-site-using-s3-route-53-acm-cloudfront-411a), or refer to [my Github repo for the CDK code](https://github.com/SathyaBhat/cdk-cdn) that I used to build the entire infra.


### Commenting

For comments, there are a bunch of open-source self-hosted solutions - [Utterances](https://utteranc.es/) looks like the coolest of the lot, with comments powered by Github issues. Utterances requires a bit of theme hacking, so I didn't enable it. For now, I stuck to my existing Disqus account and might consider revisiting this later.
