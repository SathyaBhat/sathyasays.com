---
title: Getting Terraform to apply only when a change exists
author: Sathya
type: post
date: 2020-11-30T00:00:00+00:00
url: /2020/12/30/terraform-apply-only-on-change
featured_image: https://images.sbhat.me/ss/neon-city/neon-city-box.jpg
categories:
  - "Tips & How-To's"
tags:
  - Terraform
  - Linux
  - Bash
  - Make
---

### The POC

Over the past couple of weeks I'd been working on getting our alerts deployed with Terraform. The initial proof of concept was a very simple shell script with a lot of copy-paste to handle the many accounts, environments and regions that I work on. As I started to work through the production accounts, the terraform plan was taking several minutes do to the number of resources that we have and the number of alerts covering these alerts. Before that, let's take a look at the base shell script that I had when starting to work on this. 

```bash
terraform init -reconfigure
terraform plan
terraform apply
```


Simple and straightforward, the script would do a `terraform init`, `plan` and `apply`. This was still in early dev stages and I was running on our dev environment so I didn't have to worry about approvals and what not. Plus the only resources that I was deploying was CloudWatch alerts, so the worst case scenario was that the alerts would be destroyed but they weren't in-place for our alerting anyway.

As more resources and alerts were being added, the plan and subsequent apply was taking more time, especially since the resources that existed had to be checked for first. I started looking at was in improving this and first obvious idea was to not apply if there's no changes to be done - and since terraform plan knows about the possible changes to be applied, looking at terraform plan help, I saw an option for detailed exit code and thought that would do! But what are exit codes?

Exit status and Exit codes

When a command is run in a shell and the command has exited, the shall captures whether the command was successful or not, using exit codes. This status is known as the exit status. The implementation varies across various shells, but most Linux shells report a non-zero status for a command that did not work as expected and a zero status for a successful command. The error code can be checked for using the shell variable `$?`. Confused? Consider the below example:

Example 1: 
```bash
sathyabhat in ~
❯ ls ~
...

sathyabhat in ~
❯ echo $?
0
```

Example 2:
```
sathyabhat in ~
❯ ls ~/non
ls: cannot access '/home/sathyabhat/non': No such file or directory

sathyabhat in ~
❯ echo $?
2
```

In example 1, the `ls` command ran successfully and thus returned an error code of `0`. This is stored in the shell variable `$?`, which you can echo and see the error code. if you've customized your shell prompt to show the exit status and code, you can see these printed right away and the shell customizations make use of these variables to show the error code.

In example 2, the `ls` command could not find the file/directory and thus not only gave a feedback about the missing file, but the exit code was also set to a non-zero value, i.e. 2. The [manual page](https://man7.org/linux/man-pages/man1/ls.1.html) for `ls` documents the non-zero exit codes used:


Exit status:

    0      if OK,

    1      if minor problems (e.g., cannot access subdirectory),

    2      if serious trouble (e.g., cannot access command-line
          argument).


