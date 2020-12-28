---
title: Getting Terraform to apply only when a change exists
author: Sathyajith Bhat
type: post
date: 2020-12-28T00:00:00+00:00
url: /2020/12/30/terraform-apply-only-on-change
categories:
  - "Tips & How-To's"
tags:
  - Terraform
  - Linux
  - Bash
  - Make
---

### The Simple Plan and Apply

Over the past couple of weeks I'd been working on getting our alerts deployed with [Terraform](https://www.terraform.io/). The initial proof of concept was a very simple shell script with a lot of copy-paste to handle the many accounts, environments and regions that I work on. As I started to work through the production accounts, the terraform plan was taking several minutes do to the number of resources that we have and the number of alerts covering these alerts. Before that, let's take a look at the base shell script that I had when starting to work on this. 

```bash
#!/bin/bash
terraform init -reconfigure
terraform plan
terraform apply -auto-approve
```

Simple and straightforward, the script would do a `terraform init`, `terraform plan` and `terraform apply`. This was still in early dev stages and I was running on our dev environment so I didn't have to worry about approvals and what not. Plus the only resources that I was deploying was [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) alerts, so the worst case scenario was that the alerts would be destroyed but they weren't in-place for our alerting anyway.

As more resources and alerts were being added, the plan and subsequent apply, was taking more time. In addition, the `terraform apply` was being run even if there were no changes to be applied and this was adding few minutes to run since since the resources that existed had to be checked for change, during plan and apply phases. I started looking at improving this and the most immediate idea was to not run the `terraform apply` if there were no changes to be done. Since Terraform knows about the possible changes to be applied post running `terraform plan`, I started looking at terraform plan documentation to look for any interesting tit-bits. I saw an option for detailed exit code and thought to myself - this would do! But what are exit codes?

### Exit status and Exit codes

When a command is run in a shell and the command has exited, the shall captures whether or not the command was successful using exit codes. This status is known as the exit status. The implementation varies [across various shells, languages and Operating Systems](https://en.wikipedia.org/wiki/Exit_status), but most Linux shells report a non-zero status for a command that did not work as expected and a zero status for a successful command. The error code can be checked for using the shell variable `$?`. Confused? Consider the below example:

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

In example 1, the `ls` command ran successfully and thus returned an error code of `0` (and thus, a "zero-return" code). This is stored in the shell variable `$?`, which you can echo and see the error code. 

In example 2, the `ls` command could not find the file/directory and thus not only gave a feedback about the missing file, but the exit code was also set to a non-zero value, i.e. 2. The [manual page](https://man7.org/linux/man-pages/man1/ls.1.html) for `ls` documents the non-zero exit codes used:


    Exit status:

    0      if OK,

    1      if minor problems (e.g., cannot access subdirectory),

    2      if serious trouble (e.g., cannot access command-line
          argument).

If you've customized your shell prompt to show the exit status and code, you can see these printed right away and the shell customizations make use of these variables to show the error code.

### Conditional apply with Terraform

Now that we understand the exit codes better, let's take a look at what terraform's detailed exit code documentation says:


```bash 
sathyabhat in ~

❯ terraform plan -help

Usage: terraform plan [options] [DIR]

  Generates an execution plan for Terraform.


Options:

  -detailed-exitcode  Return detailed exit codes when the command exits. This
                      will change the meaning of exit codes to:
                      0 - Succeeded, diff is empty (no changes)
                      1 - Errored
                      2 - Succeeded, there is a diff
```

So terraform will return a zero-error code if there's no changes to be applied, and will return a 2 if there's a diff that needs to be applied. Knowing this, we can modify our shell script to check for the exit code and then do a apply only if exit code is 2

```bash
#!/bin/bash
terraform init -reconfigure
terraform plan
if [ $? -eq 0 ]; then
  echo "No changes, not applying"
elif [ $? -eq 1 ]; then
  echo "Terraform plan failed"
  exit 1
elif [ $? -eq 2 ]; then
  terraform apply -auto-approve
fi
```

So, there you go - with this simple tweak, terraform will run the apply command if there's nothing to be done. 
