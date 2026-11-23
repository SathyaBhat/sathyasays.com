+++
title = "The re:Invent 2026 Attendee Guide: Agentic Reliability Engineering"
author = "Sathyajith Bhat"
type = "post"
date = 2026-11-12
url = "/reinvent-2026-attendee-guide-agentic-reliability-engineering/"
summary = "Here's my suggestions for a few sessions at re:Invent 2026 focusing on Agentic Reliability Engineering"
categories = ["AWS"]
tags = ["aws", "reinvent", "agentic", "reliability", "engineering"]
+++

[AWS re:Invent 2026 is here](https://aws.amazon.com/events/reinvent/) and runs from Nov 30 to Dec 4. I've been publishing re:Invent attendee guides for years, and this one is no different. Given all the emphasis on _agentic_ engineering, this guide focuses on reliability engineering with emphasis on AI agents to do reliability work: incident response, remediation, disaster recovery, observability, and making agents themselves resilient. Sessions marked with a repeat have more than one slot. While all sessions are already booked, a good chunk of them are reseved for walk-ups, so join the walk-up line if seats show as unavailable.

### General Guidance

**Tips for your first AWS re:Invent**

If you're a first-time attendee at re:Invent, you might be very tempted to fill your calendar with numerous sessions. I made the same mistake and realized I was burnt out by day three. AWS re:Invent is not just another tech conference; it's better to pace yourself and limit your schedule to two or three sessions a day for the first day or two. You can gradually increase the number of sessions on subsequent days. Trust me; you'll never run out of sessions to attend!

Regarding session types, I would recommend giving priority to Chalk Talks, Builders' Sessions, Workshops, or Lab sessions over Breakout sessions. You can always watch the breakout sessions on demand later, but the experience of collaborating and discussing with fellow attendees in the other sessions is invaluable.

Builders' sessions deserve a special mention. They are 60-minute hands-on sessions where you build alongside AWS experts, so bring your laptop. In 2026 most of them have a team of about five AWS experts listed, and more than half run in the open Content Hub spaces instead of a closed breakout room. Like chalk talks and workshops, they aren't recorded, so they're worth prioritizing over breakouts. Every builders' session takes reservations; if it shows as full, join the walk-up line.

I also suggest watching the keynotes on topics that interest you. The lines for Keynote viewing can be quite long, so it's best to catch them in the comfort of your hotel room or in the overflow rooms if you have a session scheduled immediately after the keynotes.
New for this year is that Dr Werner Vogels, CTO of Amazon, will not be doing is trademark keynote that I never miss out listening in person. The keynotes are:

* CEO Keynote by Matt Garman on new launches and the innovations powering the agentic era, from AI infrastructure to agents.
* Developer Keynote featuring some favourite Developer Advocates and Principal/Distinguished Engineers
* Data & AI Keynote by Swami Sivasubramanian, VP of Amazon AI, on the latest in generative AI and agentic AI.
* Partner Keynote featuring AWS Partners (I always skip this as I don't work with partners)
* Technical Innovations Keynote featuring undering-the-hood look at AWS infrastructure

 
Keep in mind that AWS may launch new services during re:Invent week, and some of these services might address long-standing problems. So, make sure to leave room in your schedule for a session or two about the newly launched services.

Also note that the venues where the talks happen are quite expansive and it can take a good 30-45 minutes to transition from one venue to the other – with this in mind, I would highly recommend grouping interesting sessions in a venue rather than jumping across venues multiple times a day.

And as I mentioned earlier, don't give up on a session just because the catalog shows no seats left. Reservable sessions keep a walk-up (standby) line at the door, and seats held for people who don't show up are released to that line shortly before the session starts. Arrive 10-15 minutes early and join the line; you'll get in more often than you'd expect.

### Come say hi!

I missed the past two re:Invents but I'll be back this year - as a speaker too. Come join me at my session 

[IND3337 | The Trade Desk's Cloud Journey: AI-Assisted Optimization to AI Agents](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=IND3337)
When: Mon Nov 30 4:30 PM, Caesars Forum (Level 1, Forum 120, Content Hub Blue Theater) | Breakout, 300, no reservation needed

> The Trade Desk operates a real-time advertising platform on AWS, where infrastructure must handle massive scale while making bidding decisions in milliseconds. At that volume, cloud cost optimization is a continuous discipline, not a one-time audit. In this breakout, The Trade Desk shares how it moved from manual cost audits to an AI-assisted approach: an internal MCP server that lets AI agents investigate cost and usage data, surface savings across services like S3, NAT Gateway, EBS, and Graviton, and apply a repeatable method for optimizing workloads over time. You'll see how the team structured the agents, what they found, and where the approach is headed.

## My Recommendations

With the emphasis on agentic engineering, there are a lot of sessions that focus on reliability engineering with AI agents. Here are my recommendations for sessions to attend:

### Workshops

[IND327 | Build a team of agents: From incident diagnosis to safe remediation](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=IND327)
When: Mon Nov 30 8:00 AM, Wynn (Cristal 1) | Tue Dec 1 12:00 PM, Wynn
> Most AI agents stop at the root cause report, leaving engineers to act under pressure. In this workshop, build three cooperating agents on a pre-provisioned workload using Strands Agents on Amazon Bedrock AgentCore with Amazon CloudWatch and Amazon Application Recovery Controller. A live app throws 4XX errors and a troubleshooting agent runs root cause analysis. Then build a remediation agent to apply the fix. When 5XX errors signal an Availability Zone impairment, you'll extend the remediation agent to consult a resilience agent before acting. Leave with a working reference implementation you can adapt to your financial services or enterprise environment.

[COP317 | Hands-on with AWS DevOps agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP317)
When: Mon Nov 30 3:30 PM, Wynn (Margaux 2) | Wed Dec 2 12:00 PM, MGM
> AWS DevOps Agent is your always-available operations teammate that investigates, resolves, and proactively prevents incidents. In this hands-on workshop, take the on-call seat: inject real faults into a live microservices store on Amazon EKS, partner with the agent to root-cause them in minutes, and judge its mitigation plans. Then extend it — encode your team's expertise as skills, connect custom MCP tools, automate investigations from alarms, and approve agent-executed fixes. Leave with production-ready patterns that keep your infrastructure running.

[ARC311 | When agents disagree: Resolving competing goals in cloud operations](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=ARC311)
When: Mon Nov 30 12:30 PM, Wynn (Cristal 3) | Wed Dec 2 3:00 PM, Wynn
> When two agents manage the same workload, each optimizing a different objective, conflicting actions are the default, not the exception. A consensus layer changes the pattern: pillar-aligned agents carry workload goals and live signals as context, reason toward agreement, and produce a single decision playbook before any action executes. In this session, you build one pillar agent from scratch, configure its context layer, connect it to the consensus flow, and watch shared context resolve a live disagreement without rules or priority overrides. Bring your laptop to participate.

[COP357 | Observe AI agents and workloads end to end](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP357)
When: Wed Dec 2 8:30 AM, MGM (Grand 111) | Wed Dec 2 12:00 PM, MGM
> Get hands-on with Amazon CloudWatch Omni, the next evolution of CloudWatch that monitors your AI stack end to end, from the agent all the way down to the self-hosted inference workload serving it, converging application and agent observability into one AI-powered solution. Instrument an agent, trace its execution, and run evaluations against golden datasets. When something degrades, explore auto-discovered topology and golden metrics to pinpoint where latency or errors creep in. Navigate from alarm to the responsible inference workload, and let Omni's AI-powered investigation trace the root cause.

[COP364 | Build better, review faster: AI-Powered Well-Architected reviews](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP364)
When: Tue Dec 1 3:00 PM, MGM (Grand 113) | Thu Dec 3 3:00 PM, MGM
> Periodic reviews can't keep pace with infrastructure that changes daily. In this hands-on workshop, stand up the AWS Well-Architected Agent for continuous, goal-driven reviews across a multi-account environment. Configure agent profiles, cross-account role chaining, and business goals that prioritize across Cost Optimization, Security, Resilience, and Performance pillars. See how the agent enriches Trusted Advisor, Compute Optimizer, and Resilience Hub signals with cross-pillar trade-off analysis. Run pre-deployment reviews against CloudFormation, CDK, and Terraform, then remediate through AI-generated SOPs. Wire recommendations into CI/CD via the Well-Architected API. For architects, platform engineers, and operations leads who want always-on architectural governance in their delivery lifecycle.

[DAT432 | Build eval-driven skills for Aurora PostgreSQL operations](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=DAT432)
When: Thu Dec 3 12:00 PM, MGM (Premier 317)
> Turn Aurora PostgreSQL runbooks into agent skills and test whether they improve an agent's advice. Work through three incidents on a live cluster: RDS Proxy session pinning that starves checkout connections, a payout job whose open transaction blocks checkouts, and stalled order delivery alongside a long-running transaction that holds back vacuum cleanup. Complete and refine skills that cover pre-flight checks, execution, validation and rollback. Freeze a grading rubric, then compare the same agent, hosted on Amazon Bedrock AgentCore, without and with your skill. Write Python recovery checks that reject incomplete fixes, perform the repairs yourself, and verify customer recovery using independent database and business records.

### Builders' Session

[ARC314 | Architect resilient agentic systems: Patterns beyond the happy path](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=ARC314)
When: Mon Nov 30 2:30 PM, Wynn (Cristal 2) | Wed Dec 2 12:00 PM, Wynn
> Every agentic system works on the happy path. The real test is what happens when your AI agent times out mid-reasoning, returns a malformed action, or cascades a single failure across an entire chain. In this session, you implement four resilience patterns built for non-deterministic agents: circuit breakers that trip on semantic failure, fallback hierarchies from AI to rules to human, bulkhead isolation between agents, and timeout budgets for chain-of-thought latency. Leave with a decision framework mapping failure modes to pattern combinations you can implement immediately. Bring your laptop to participate.

[COP320 | Custom SRE agents: From prompt to proactive ops with DevOps agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP320)
When: Mon Nov 30 3:00 PM, Wynn (Latour 7) | Wed Dec 2 3:00 PM, Wynn
> In this builder session, learn how to create custom SRE agents that turn a simple prompt into automated, environment-specific operational workflows. Using pre-configured tools and integrations, you'll define agents tailored to your priorities, whether that's anomaly detection, performance optimization, cost analysis, or resiliency recommendations. See how agents combine real-time observability data with structured reasoning to surface actionable improvements without manual investigation. Walk away with hands-on experience designing an agent that monitors your operational patterns and proactively recommends next steps, so your team spends less time diagnosing and more time shipping.

[CON319 | Amazon EKS incident response and remediation with AWS DevOps Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=CON319)
When: Mon Nov 30 11:30 AM, Caesars Forum (Alliance 311) | Thu Dec 3 4:00 PM, MGM
> When an incident hits, engineers lose time pivoting between kubectl, metrics, logs, and traces to find root cause. In this builder session, you'll drive the AWS DevOps Agent through a production-realistic incident end to end: detect the anomaly from observability signals, correlate metrics, logs, and traces to a root cause, and execute automated remediation with a human-in-the-loop gate. You'll wire the observability inputs the agent consumes, review its diagnosis journal, and validate recovery. Leave with a repeatable detect-diagnose-remediate-verify pattern and a permission-scoped remediation playbook you can adapt to your own clusters.

[SVS322 | Build self-healing Serverless applications with AWS DevOps Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=SVS322)
When: Mon Nov 30 4:30 PM, Caesars Forum (Forum 120) | Wed Dec 2 8:30 AM, MGM
> Production incidents at 2 a.m. don't wait for your team to wake up. In this builders' session, work with a deployed serverless application and use AWS DevOps Agent to resolve real-world failures autonomously. You'll inject common production issues—such as Lambda throttling, timeout cascades, DynamoDB throughput exceeded, and SQS dead-letter queue buildup—then configure the agent to perform root cause analysis, propose remediation, and apply fixes. You'll tune detection sensitivity, set approval gates for automated actions, and evaluate where autonomous remediation is safe versus where human oversight is required. Bring your laptop.

[STG335 | Build an AI-powered AWS Backup analyst and remediate with AgentCore](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=STG335)
When: Mon Nov 30 4:30 PM, MGM (Room 304) | Thu Dec 3 8:30 AM, MGM
> Few teams have the capacity to continuously audit their backup posture across accounts and regions. AI agents can do that work and recommend fixes while keeping you in control. In this builders' session, you'll construct a multi-agent system that analyzes your AWS Backup environment across four dimensions: coverage gaps, ransomware resilience scoring, vault security, and cost optimization. You'll build an MCP server exposing backup APIs as agent tools, wire specialist subagents into an orchestration graph, and run a remediation agent with human-in-the-loop approval on AWS Bedrock AgentCore Harness. The system runs in your own environment after the session.

[DAT428 | Build governed remediation workflows for Aurora database operations](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=DAT428)
When: Thu Dec 3 9:00 AM, MGM (Chairman's 363)
> AI-powered database intelligence can surface recommendations for Aurora performance issues, but acting on those recommendations safely in production requires governance. In this session, build a governed recommendation-to-remediation workflow for Aurora PostgreSQL. Starting from a performance investigation, review recommendations and apply remediation through human-in-the-loop approval gates backed by scoped IAM permissions and API guardrails. The session covers capturing an auditable trail from insight to action, and planning for post-change verification and rollback actions when needed. Bring a laptop to participate.

### Chalk Talks

[ARC317 | Fault-tolerant AI agents: Choosing the right recovery pattern](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=ARC317)
When: Wed Dec 2 1:30 PM, Caesars Palace (Octavius 9) | Thu Dec 3 1:00 PM, Wynn
> When an AI agent crashes at step 20 of 30, you can't just start over. Once state accumulates, an unexamined retry becomes dangerous. Most teams default to the wrong recovery strategy because they apply stateless retry thinking to stateful workflows. In this session, we compare three approaches: replay-based recovery with idempotent tool execution, checkpoint-and-resume with human-in-the-loop pause/resume, and event-driven compensation across trust boundaries. We'll whiteboard each pattern, map it to real failure scenarios, and build a decision framework based on your agent's state model and fault domain.

[IND317 | Automate disaster recovery with Amazon Bedrock AgentCore](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=IND317)
When: Tue Dec 1 4:00 PM, Wynn (Latour 5) | Wed Dec 2 11:30 AM, Wynn
> Financial institutions face stringent regulatory requirements for operational resilience, demanding reliable disaster recovery with tight RTO/RPO targets across complex application portfolios. Yet failover procedures often remain manual and prone to error under pressure. In this chalk talk, we explore how to design a multi-agent system on Amazon Bedrock AgentCore that orchestrates end-to-end disaster recovery automation for regulated workloads. We'll walk through how a coordination agent delegates to specialized sub-agents for readiness verification, infrastructure operations, Terraform code generation, Git operations, and deployment validation—each with human-in-the-loop approval gates.

[IND365 | Operational resilience in regulated environments with AWS DevOps Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=IND365)
When: Mon Nov 30 4:30 PM, Wynn (Chopin 4) | Tue Dec 1 12:00 PM, Wynn
> As software delivery accelerates, financial services organizations struggle to manage incidents across fragmented toolchains. In this chalk talk, learn how AWS DevOps Agent acts as an always-on operations teammate for regulated environments—resolving incidents autonomously, strengthening systems proactively, and validating releases before they reach production. We'll whiteboard four patterns: how the agent investigates and resolves incidents in minutes; how the agent learns from past incidents to recommend improvements; how on-demand SRE tasks give your team instant operational intelligence; and how release readiness reviews catch compliance and dependency risks before code ships. Bring your operational challenges and leave with best practices.

[COP331 | AIOps strategy: foundations before capabilities](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP331)
When: Wed Dec 2 4:30 PM, Wynn (Chopin 4) | Thu Dec 3 1:30 PM, Wynn
> Most teams turn on AI-driven operations before thinking about how they will scale. This chalk talk works through an AIOps strategy at the whiteboard, using real support-case patterns showing that most critical failures are catchable before they reach production. We discuss areas your strategy should consider that will allow you to scale to additional capabilities more quickly and where Frontier Agents could help. Leave with a foundational framework and a maturity discussion for your team.

[COP339 | Logging strategy for agentic investigations](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP339)
When: Thu Dec 3 1:00 PM, Wynn (Montrachet 1)
> Most logging strategies get built one team at a time. Each team picks its own destination and format, so an AI agent investigating an incident has to search across accounts and reason over a dozen schemas. In this chalk talk, we'll whiteboard a CloudWatch logging design that centralizes logs and enriches them on ingest with service context, so your agents start every investigation with what they need. We'll debate what to transform at ingest versus keep raw, and which logs earn hot storage. Bring the log setup you run today and we'll redraw it with you.

[AIM436 | Scale production agents reliably with AgentCore](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=AIM436)
When: Mon Nov 30 10:00 AM, MGM (Boulevard 163) | Wed Dec 2 3:00 PM, Wynn
> What changes when you go from ten agent sessions to ten thousand? In this chalk talk, whiteboard the architectural and operational patterns that determine whether your agents perform reliably at scale. Discuss microVM isolation for secure multi-tenancy, elastic scaling that handles traffic spikes without capacity planning, and long-running task handling with human-in-the-loop checkpoints. Cover resiliency patterns: what happens when a tool call fails, how to handle model timeouts, and designing for graceful degradation. Walk through the infrastructure decisions you make once and benefit from forever. Bring your scaling scenarios and we architect solutions together.

[INV521 | Teaching Telemetry to Think: From Raw Signals to Root Cause](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=INV521)
When: Wed Dec 2 1:00 PM, Wynn (Latour 5) | Thu Dec 3 10:30 AM, MGM
> An AI agent investigating an incident starts cold: no sense of normal, no topology, no causal history. It rebuilds context from raw documents every time. What if the telemetry understood itself first? We'll examine an intelligence layer for agentic observability, where streaming detectors and a live service graph distill billions of signals into incident observations, then fine-tuned reasoning models, built on open-weight LLMs, correlate them into ranked root causes. Whiteboard with us on the hard parts: what to teach a model versus retrieve at inference, how domain fine-tuning beats frontier scale, and where reasoning models still fail.

### Code Talks

[COP405 | When agents run code: sandboxes for reliable DevOps](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP405)
When: Mon Nov 30 3:00 PM, Wynn (Margaux 1) | Thu Dec 3 3:00 PM, Wynn
> LLMs hallucinate. Code doesn't. When your AI agent investigates a production incident, some answers demand computation, not just reasoning. In this code talk, we crack open the sandbox in AWS DevOps Agent: an ephemeral, investigation-scoped Linux environment where the agent writes and runs code inside a Lambda MicroVM with read-only AWS access and zero lateral blast radius. We'll discuss how networking allowlists, pre-installed packages, and executable skills give you deterministic, auditable results for log parsing, metric correlation, and multi-source analysis. Bring your problems and we'll whiteboard the isolation boundaries live.

[COP406 | Rethink release management for the agentic coding era](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP406)
When: Mon Nov 30 8:30 AM, Wynn (Cristal 2) | Tue Dec 1 4:30 PM, MGM
> GitOps was designed for human-speed change. Agentic coding tools now generate pull requests faster than any team can review and safely release. Your release process is the new bottleneck. In this code talk, we'll live-code a GitOps release workflow where AWS DevOps Agent acts as an intelligent release manager, validating the results through a release pipeline at every promotion gate. Instead of manual approvals, DevOps Agent uses production intelligence (runtime dependencies, service health, deployment risk) to make real-time go/no-go decisions. Learn how to wire DevOps Agent into your GitOps reconciliation loop so releases match the velocity of agentic code generation without sacrificing safety.

[COP407 | Build-time context for faster agentic incident response](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP407)
When: Thu Dec 3 10:30 AM, Wynn (Margaux 1)
> AI agents can fix production issues, but only with the right context. In this talk, an AI agent builds a feature and, in the same pull request, creates the context it needs on call: instrumentation, alarms, dashboards, and skills, all as code. Then you break the live app. Watch an agent use those skills with Amazon CloudWatch Omni and AWS DevOps Agent to triage, find the root cause, and ship the fix. Leave with patterns that give agents the context to operate what they build.

[CON339 | Fleet-wide AIOps for Amazon EKS with the AWS DevOps Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=CON339)
When: Mon Nov 30 4:30 PM, Wynn (Margaux 1)
> Operating one EKS cluster is manageable. Operating a fleet of them is where the hard problems live: failures that surface far from their cause, VPC CNI IP exhaustion, Karpenter churn, and upgrades that stall across clusters. This chalk talk shows how AIOps and the AWS DevOps Agent bring order to operations at fleet scale. See how the DevOps Agent correlates signals across clusters to find root cause instead of chasing symptoms. Learn how it turns noisy telemetry into a diagnosis and a recommended fix. Discover the guardrails that let agents act on your fleet safely, with the blast radius bounded.

[COM328 | Autonomous Remediation with OpenTelemetry and DevOps Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COM328)
When: Mon Nov 30 12:00 PM, Caesars Forum (Forum 120) | Wed Dec 2 4:30 PM, MGM
> You instrumented everything. You have metrics, logs, and traces. And when production breaks a human still has to piece it together, tab by tab, signal by signal, under pressure. That is not an observability problem, it's an automation problem. We'll show you an architecture on AWS that closes it. OpenTelemetry captures signals across EKS, ECS, and Lambda. AWS DevOps Agent runs the investigation, finds the root cause, and prepares the fix. By the time a human looks at it, the pull request is ready. Come learn the triggers, investigation loop, and guardrails you need before letting an agent touch production.

### Breakout sessions

[COM308 | What Building an SRE Agent Taught Us About Agents at Scale](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COM308)
When: Wed Dec 2 2:30 PM, Caesars Forum (Forum 120, Orange Theater)
> Anyone can wire up an agent, but operating one safely and cheaply across thousands of sessions is where developer craft begins. Grounded in a production SRE agent we built on Amazon Bedrock AgentCore and the Strands Agents SDK, this session dissects engineering around agentic models: session isolation, context management, and least privilege identity. What broke, and how we fixed it: an agent with too much access, context bloat that wrecked cost, a crash during a tool call that forced durable recovery. You will see where architectures leak, how to evaluate on production traces, and tradeoffs behind resilient agent infrastructure.


[COP302 | Best practices for agentic-driven operations](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=COP302)
When: Thu Dec 3 10:30 AM, Caesars Palace (Octavius 4, Blue Theater)
> AI agents are moving from assistants to operators, but how do they actually work within your operational workflows? Understand the architecture of agents that detect anomalies, diagnose root cause across distributed systems, and execute remediation like rollbacks, scaling, and traffic shifts. Learn how agents reason over telemetry, sequence actions, and determine when to escalate. Explore best practices for shaping agent behavior through guardrails, approval gates, and feedback loops as core design elements. Leave with a framework for evaluating where agents should act autonomously versus where human judgment remains essential.

[IND3348 | A Context Gap, Not a Data Gap: Riot Games Rethinks Incident Learning](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=IND3348)
When: Thu Dec 3 10:30 AM, Caesars Forum (Forum 120, Light Blue Theater)
> Live-service teams excel at detecting incidents and restoring service, but using each review to improve the next response remains difficult. Riot Games has extensive telemetry, incident records, triage practices, and root cause analysis, yet analysts must still connect evidence across systems. Riot Games and AWS share an AI-assisted post-incident review approach that brings evidence together, provides traceable recommendations, and keeps decisions with human reviewers. Explore how preserving uncertainty, linking claims to source evidence, and using Amazon Bedrock AgentCore as a reusable foundation can help teams close context gaps and improve operational learning.

[ARC328 | Stop fixing, start preventing with Well-Architected Agent](https://reinvent-planner.cloud/aws/reinvent/2026/sessions?shortId=ARC328)
When: Wed Dec 2 1:30 PM, MGM (Chairman's 363, Light Blue Theater)
> Reactive incident response grows more expensive as environments scale. AWS Well-Architected Agent shifts resilience and security from periodic review to continuous, automated assessment. Its agentic reasoning identifies single points of failure, recovery gaps, and vulnerabilities across 100+ services, ranking findings by workload criticality and business goals. Crucially, each recommendation includes cross-pillar trade-off analysis - showing cost and performance implications — so you improve resilience and security without unintended consequences elsewhere. Walk away able to catch risks before they become incidents.

