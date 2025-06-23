---
title: Talk to your AWS Resources using Amazon Q Developer Chat
author: Sathyajith Bhat
type: post
date: 2025-06-23
url: /amazon-q-developer-chat-adhoc-querying/
summary: Tired of wrangling JSON blobs representing AWS resources? Amazon Q Developer Chat can help!
featureimage: https://i.sathyabh.at/ss/amazon-q-logo.jpg
categories:
  - GenAI
tags:
  - amazon q developer chat
  - aws
  - amazon q
---

Amazon Q is Amazon's [generative AI assistant](https://aws.amazon.com/q/). Amazon Q comes in various flavours, all (unfortunately) having the same branding as "Amazon Q". I say unfortunately because all of my experience in trying to use Amazon Q in the AWS Console has been pretty bad.

While Q in AWS Console has been pretty bad, the CLI experience using [Amazon Q Developer](https://github.com/aws/amazon-q-developer-cli) has been pretty good. A few months back, I saw a post from [Nathan Peck](https://www.linkedin.com/in/nathankpeck/) talking about Amazon Q Developer's [agentic chat feature](https://www.linkedin.com/posts/nathankpeck_amazon-q-developer-cli-has-a-powerful-new-activity-7303438958904889344-y0Pl). I was skeptical at first but a few queries later, I was covinced. Since then I've been using it pretty regularly and been quite happy with it. I talk about a few of the ways of how I have been using it.

Amazon Q Developer Chat is a conversational interface that allows you to interact with your AWS resources using natural language. It uses Amazon Q's generative AI capabilities to understand your queries and provide accurate responses.

### Pre-requisites

- Install [Amazon Q Developer](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html)
- Authenticate to AWS

Next, Launch Amazon Q Developer in chat mode by typing

```bash
q chat
```

You can select the model Q chat uses by typing `/model` in the chat window.

```log
/model

? Select a model for this chat session ›
❯ claude-4-sonnet (active)
  claude-3.7-sonnet
  claude-3.5-sonnet
```

### Examples

Now, the world is your oyster! I've found Q Developer Chat to be particularly useful for ad hoc querying. Sure, I can use `aws cli` and use `JMESPath` to [query AWS resources](https://sathyasays.com/2023/09/04/bulk-tag-instances-in-asg-aws-cli/) or use `jq` - but it's something that I do rarely and always mess up with the syntax and takes me a lot of time to get it right. Now with Q chat, I can ask it to do the same thing for me. Here's an example - I found an idle EC2 instance and wanted to know how much it costs to run it for a month. I can look up the instance type and then calculate the cost using [calculator.aws](https://calculator.aws/#/) - but it gets fiddly. Or, I can ask Q chat to do it for me.

> There's an instance i-02c7834146d04fa8e8 in us-east-1. Tell me how much it costs to run monthly, including attached storage and break the costs down by box usage & storage

Amazon Q's response:

> I'll help you get the cost breakdown for that EC2 instance. Let me first gather information about the
instance and its attached storage.


Amazon Q Developer Chat is _agentic_ - it can run commands (called tools) for you and access the data. This is what makes it so much more powerful than just asking yet another LLM. Instead of assuming and guessing, Q Developer Chat can actually look up details and be accurate. In this case, it looks up the instance details using `aws ec2 describe-instances` & `aws ec2 describe-volumes` and pulls up the required data. The tools can be marked as trusted/untrusted. Trusted tools run without confirmation, for untrusted commands, Q will always ask for confirmation. Here's what happens as it's running the tools:

```text
🛠️  Using tool: use_aws (trusted)
 ⋮
 ● Running aws cli command:

Service name: ec2
Operation name: describe-instances
Parameters:
- instance-ids: ["i-02c7834146d04fa8e8"]
Profile name: default
Region: us-east-1
Label: Get EC2 instance details
 ⋮
 ● Completed in 2.480s
Now let me get details about all the
attached EBS volumes to calculate storage costs:


🛠️  Using tool: use_aws (trusted)
 ⋮
 ● Running aws cli command:

Service name: ec2
Operation name: describe-volumes
Parameters:
- volume-ids: ["vol-12345","vol-56789","..."]
Profile name: default
Region: us-east-1
Label: Get EBS volume details
 ⋮
 ● Completed in 2.85s
```

> Based on the information gathered, here's the monthly cost breakdown for EC2 instance i-02c7834146d04fa8e8:

So in about 4 seconds, Q Developer Chat ran the aws commands to get the instance details and the EBS volume details, and then calculated the monthly cost breakdown. The results are as follows:

```
### Instance Details
• **Instance Type**: i3.4xlarge (Windows)
• **State**: Currently stopped
• **Tenancy**: Dedicated
• **Location**: us-east-1e

## Monthly Cost Breakdown

### EC2 Instance Cost
• **Instance Type**: i3.4xlarge on dedicated tenancy
• **Estimated Monthly Cost**: ~$1,094.40
  • i3.4xlarge on-demand: ~$1.248/hour × 730 hours = $911.04
  • Dedicated tenancy premium: ~$183.36 additional
  • Windows licensing: Included in Windows instance pricing

### Storage Costs (EBS Volumes)
Root Volume:
• 1 × 1,000 GB gp3 volume: $80.00/month

Data Volumes (19 volumes):
• 19 × 6,144 GB gp3 volumes = 116,736 GB total
• Storage cost: 116,736 GB × $0.08/GB = $9,338.88/month
• IOPS cost: 19 volumes × 16,000 IOPS × $0.005 = $1,520.00/month
• Throughput cost: 19 volumes × 250 MB/s × $0.04 = $190.00/month

Total Storage Cost: $11,128.88/month

## Total Monthly Cost Summary
• **EC2 Instance**: $1,094.40
• **EBS Storage**: $11,128.88
• **Total Monthly Cost**: ~$12,223.28

## Cost Breakdown by Category
• **Compute (Instance)**: $1,094.40 (8.9%)
• **Storage**: $11,128.88 (91.1%)
```

> This is a storage-heavy workload with nearly 117 TB of attached GP3 storage across 20 volumes. The storage costs dominate due to the large volume sizes and high IOPS provisioning (16,000 IOPS per data volume). This appears to be a database server given the MSSQL application tag and multiple data volumes configuration.

> For more precise pricing estimates, I recommend using the [AWS Pricing Calculator](https://calculator.aws) as prices can vary based on specific configurations and any applicable discounts or reserved instance pricing.


Not only did it give me a summary of the costs, it also brokedown the costs by category (specifically asked for in the prompt), it also surfaced details that I did not know (tenancy being dedicated) and gave a good summary of the instance based on its spec and the tags associated with it.

Here's another case of Q Developer Chat coming to the rescue - I wanted to check if the EBS volume spec on one instance matched that on the other instance. I gave Amazon Q a spin:

> Can you tell me how many EBS volumes are attached to instances i-xxx & i-yyy in us-east-1 and the specifications of those?

Couple of seconds later

> Based on the information I've gathered, here's a summary of the EBS volumes attached to each instance: <summary of each volume details, in a new line>

Good info but hardly readable, so follow up question

> please provide a side by side listing of the instances and the ebs volume, size, iops and throughput. mention i-xxxx name as name1 and i-yyy name as name2

 Instance Name | Instance ID | Volume ID | Device | Size (GB) | Type | IOPS | Throughput (MB/s) |
|---------------|-------------|-----------|--------|-----------|------|------|-------------------|
| name1 | i-xxxx | vol-1234 | /dev/sda1 | 50 | gp3 | 3,000 | 125 |
| name1 | i-xxxx | vol-1234 | xvdf | 2,048 | gp3 | 15,000 | 500 |
| name1 | i-xxxx | vol-1234 | xvdg | 2,048 | gp3 | 15,000 | 500 |
| name1 | i-xxxx | vol-1234 | xvdk | 2,048 | gp3 | 15,000 | 500 |
| name1 | i-xxxx | vol-1234 | xvdl | 2,048 | gp3 | 15,000 | 500 |
| name1 | i-xxxx | vol-1234 | xvdp | 2,048 | gp3 | 15,000 | 500 |
| name1 | i-xxxx | vol-1234 | xvdq | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | /dev/sda1 | 50 | gp3 | 3,000 | 125 |
| name2 | i-yyy | vol-1234 | xvdf | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | xvdg | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | xvdk | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | xvdl | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | xvdp | 2,048 | gp3 | 15,000 | 500 |
| name2 | i-yyy | vol-1234 | xvdq | 2,048 | gp3 | 15,000 | 500 |

Again, this is something that I could have done with jq, but having to provide a question in natural langauge and having a conversation stating do x or do y is so much more powerful and flexible. And it allows me to multitask with other tasks while I wait for this response.

So if you've been holding out on Q Developer Chat because you've had a pretty poor experience with Q in the AWS Console, I would highly recommend you to give Amazon Q Developer Chat a try. You might be surprised by the results.
