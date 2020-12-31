---
title: Getting Terraform to apply only when a change exists using Make
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

### TL;DR

Applying some Bash knowhow on exit codes, you can cut down the time required for a Terraform apply if no changes are to be done

### The Simple Plan and Apply

Over the past couple of weeks, I'd been working on getting our alerts deployed with [Terraform](https://www.terraform.io/). The initial proof of concept was a very simple shell script with a lot of copy-paste to handle the many accounts, environments and regions that I work on. As I started to work through the production accounts, the Terraform plan was taking several minutes do to the number of resources that we have and the number of alerts covering these alerts. Before that, let's take a look at the base shell script that I had when starting to work on this. 

```bash
#!/bin/bash
terraform init -reconfigure
terraform plan
terraform apply -auto-approve
```

Simple and straightforward, the script would do a `terraform init`, `terraform plan` and `terraform apply`. This was still in early dev stages and I was running on our dev environment so I didn't have to worry about touching any critical paths. Plus the only resources that I was deploying was [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) alerts, so the worst-case scenario was that the alerts would be destroyed but they weren't in-place for our alerting anyway.

As more resources and alerts were being added, the plan and subsequent apply, was taking more time. Besides, the `terraform apply` was being run even if there were no changes to be applied and this was adding few minutes to run since the resources that existed had to be checked for change, during the plan and apply phases. I started looking at improving this and the most immediate idea was to not run the `terraform apply` if there were no changes to be applied. Since Terraform knows about the possible changes to be applied post running `terraform plan`, I started looking at Terraform plan documentation to look for any something that I could use to implement this. I saw an option for detailed exit code and thought to myself - this would do! But what are exit codes?

### Exit status and Exit codes

When a command is run in a shell and the command has exited, the shall captures whether or not the command was successful using exit codes. This status is known as the exit status. The implementation varies [across various shells, languages and Operating Systems](https://en.wikipedia.org/wiki/Exit_status), but most Linux shells report a non-zero status for a command that did not work as expected and a zero status for successful command execution. The exit code can be checked for using the shell variable `$?`. Confused? Consider the below example:

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

In example 1, the `ls` command ran successfully and thus returned an exit code of `0` (and thus, a "zero-return" code). This is stored in the shell variable `?`, which you can echo using `echo $?` and can see the exit code. 

In example 2, the `ls` command could not find the file/directory and thus not only gave feedback about the missing file, but the exit code was also set to a non-zero value, i.e. 2. The [manual page](https://man7.org/linux/man-pages/man1/ls.1.html) for `ls` documents the non-zero exit codes used:

    Exit status:

    0      if OK,

    1      if minor problems (e.g., cannot access subdirectory),

    2      if serious trouble (e.g., cannot access command-line
          argument).

If you've customized your shell prompt to show the exit status and code, you can see these printed right away and the shell customizations make use of these variables to show the exit code.

### Conditional apply with Terraform

Now that we understand the exit codes better, let's take a look at what Terraform's detailed exit code documentation says:


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

So Terraform will return a zero-error code if there are no changes to be applied, and will return a 2 if there's a diff that needs to be applied. Knowing this, we can modify our shell script to check for the exit code and then do a apply only if exit code is 2

```bash
#!/bin/bash
terraform init -reconfigure
terraform plan -detailed-exitcode
if [ $? -eq 0 ]; then
  echo "No changes, not applying"
elif [ $? -eq 1 ]; then
  echo "Terraform plan failed"
  exit 1
elif [ $? -eq 2 ]; then
  terraform apply -auto-approve
fi
```

So, there you go - with this simple tweak, Terraform will run the apply command if there's nothing to be done. But.. we're not done yet. 

### Chaining with Make

[GNU/Make](https://www.gnu.org/software/make/manual/make.html) is a build automation tool which builds executable programs and libraries by reading Makefiles and invoking targets. Make and Makefiles make it easy to invoke arbitrary targets in a clean simple way. This is excellent for pipeline automation - for example, if you need to do a `terraform plan` for a lot of accounts and environments, instead of having 

```bash
cd dev/region1
terraform plan
cd dev/region2
terraform plan
```

... 

and having to call these multiple times you can have a Makefile which says

```Makefile
plan:
    cd dev/region1
    terraform plan
    cd dev/region2
    terraform plan
```

and just invoke `make plan` from your favorite CI/CD tool. I won't get into details of Make, Karan has a nice post on [how to get started with Make and Makefiles](https://mrkaran.dev/posts/makefiles-intro/) that you can read. Coming back, for faster feedback cycle, I wrapped the terraform commands to a shell script called `call_terraform.sh`

```bash
#!/bin/bash
terraform init -reconfigure
terraform validate
terraform plan -detailed-exitcode
if [ $? -eq 0 ]; then
  echo "No changes, not applying"
elif [ $? -eq 1 ]; then
  echo "Terraform plan failed"
  exit 1
elif [ $? -eq 2 ]; then
  terraform apply -auto-approve
fi
```

created a Makefile

```Makefile
plan: 
	./call_terraform.sh
```

So now every time I do a `make plan`, I would have a Terraform init, validate and plan run instead of having to type them manually. However, this wasn't working completely as I expected - when the validate fails, the shell script would continue to the next command. I started reading up more about [set built-ins in bash](https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html). 

The set built-in allows us to change the values of shell options. In particular, the `-e` command causes an immediate exit if a command or a group of commands returns a non-zero. There's another option `-o pipefail` where the return value of the pipeline is set to non-zero if any of the commands in the pipeline fail. This can prevent masking of errors as without this set command, the pipeline's return code is that of the last command and even if an intermediate command fails, it will be set to zero, indicating successful completion of the pipeline. Even though we do not have any piped commands yet, it's a sane default to have in every shell script.

With this, our shell script is now

```bash
#!/bin/bash
set -eo pipefail
terraform init -reconfigure
terraform validate
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

Now, invoking the plan target will call the shell script, and that will result in a Terraform plan and apply - and we just want a plan. We can modify the Makefile and shell script to accept a variable called action which will then run apply only if:
- changes exist
- the action called apply is invoked.  

So our Makefile will now look like:

```Makefile
plan: 
	ACTION=APPLY ./call_terraform.sh
```

```bash
#!/bin/bash
set -eo pipefail
terraform init -reconfigure
terraform validate
terraform plan -detailed-exitcode
if [ $? -eq 0 ]; then
    echo "No changes, not applying"
elif [ $? -eq 1 ]; then
    echo "Terraform plan failed"
    exit 1
elif [ $? -eq 2 ]; then
    if [[ $ACTION == "APPLY" ]]; then
        terraform apply -auto-approve
    fi
fi
```

Now when you invoke `make plan`

```bash
❯ make plan
ACTION=PLAN ./call_terraform.sh

Initializing the backend...

Initializing provider plugins...
- Using previously-installed hashicorp/aws v2.70.0

Terraform has been successfully initialized!
------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:
  [...]
Plan: 1 to add, 0 to change, 0 to destroy.
make: *** [Makefile:2: plan] Error 2
```

`make` exits with an error.  The problem is that Make exits with an error whenever it encounters a non-zero exit code - even if it is what you want. In our case, Terraform's detailed exit code conflicts with Make's exit code check. One way to handle this is to make use of bash's "double pipes" like so

```bash
cat /this/does/not/exist || echo "This was run"
```

To be more specific, the `||` is a logical OR operator in Bash, [combined with Bash's lazy evaluation](https://unix.stackexchange.com/a/24685/1648), the command following the OR operator is not executed if the first command returns a True and the command following the pipes will run only if the preceding command exited with a non-zero exit code.

```bash
cat /this/does/not/exist || echo "This was run"
cat: /this/does/not/exist: No such file or directory
This was run
```

Contrast to an example where the first command succeeded, the second command will not run:

```bash
uname || echo "This was run"
Linux
```

Knowing this, we will save the exit code to another variable called `exit_status` since the value of `?` will be reset after every command execution. Whenever Terraform exits with non-zero code (which will happen if Terraform plan fails or has a diff), we can check the exit code to run accordingly. The shell script now looks like

```bash
#!/bin/bash
set -eo pipefail
exit_status=0
terraform init -reconfigure
terraform validate
terraform plan -detailed-exitcode || exit_status=$?
if [ $exit_status -eq 0 ]; then
    echo "No changes, not applying"
elif [ $exit_status -eq 1 ]; then
    echo "Terraform plan failed"
    exit 1
elif [ $exit_status -eq 2 ]; then
    if [[ $ACTION == "APPLY" ]]; then
        terraform apply -auto-approve
    fi
fi
```

And now when you invoke `make plan` it runs successfully! 

```bash
❯ make plan
ACTION=PLAN ./call_terraform.sh

Initializing the backend...

Initializing provider plugins...
- Using previously-installed hashicorp/aws v2.70.0

Terraform has been successfully initialized!

[...]

------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create
Plan: 1 to add, 0 to change, 0 to destroy.

❯ echo $?
0
```

For applying the changes, just do a `make apply`. When there's changes to be applied, Terraform runs as expected:

```bash
❯ make apply
ACTION=APPLY ./call_terraform.sh

Initializing the backend...

Initializing provider plugins...
- Using previously-installed hashicorp/aws v2.70.0

Terraform has been successfully initialized!

[...]
------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:
[...]
Plan: 1 to add, 0 to change, 0 to destroy.

[...]

aws_vpc.test_vpc: Creating...
aws_vpc.test_vpc: Creation complete after 5s [id=vpc-00d34db33f]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

If there's no changes, running `make apply` will not run `terraform apply`

```bash
❯ make apply
ACTION=APPLY ./call_terraform.sh

Initializing the backend...

Initializing provider plugins...
- Using previously-installed hashicorp/aws v2.70.0

Terraform has been successfully initialized!

[...]

Refreshing Terraform state in-memory prior to plan...
The refreshed state will be used to calculate this plan, but will not be
persisted to local or remote state storage.

aws_vpc.wg_vpc: Refreshing state... [id=vpc-vpc-00d34db33f]

------------------------------------------------------------------------

No changes. Infrastructure is up-to-date.

[...]
No changes, not applying
```

Hope this helped!

### References

- Bash set [builtin manual](https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html)
- Bash [logical operators](https://unix.stackexchange.com/a/24685/1648)
- [Makefile for Golang projects](https://mrkaran.dev/posts/makefiles-intro/)


Thanks to [Ninad](https://ninad.pundaliks.in/) for reviewing this post!