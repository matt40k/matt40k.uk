---
title: Serverless
author: matt40k
type: post
date: 2017-11-23T22:12:29+00:00
url: /2017/11/serverless/
categories:
  - Serverless
  - AWS
  - Azure
---

Serverless doesn’t somehow make your code run without physical servers. You still need servers, it’s just your treating your servers like you would code. However, it goes beyond just infrastructure as code (IaaS), it’s utilizing the cloud. Let’s get something clear, the cloud is nothing more than someone else’s server and for this post, I’m defining the cloud as any service provider who allows you run compute by the millisecond. The reason the cloud is such a major thing is that it allows you to treat commodity hardware as a commodity. Let me give you an idea

Problem: I have a web application, it has a few static web pages and a simple web form that interacts with a SQL database. The security team has deemed shared hosting insecure.

Traditionally, you’d buy a server, run everything on the server. Since the days of VMware you’d consider building a virtual server rather than a physical server. This could still involve purchasing a new server or additional hardware and as everyone knows, procurement can take days, weeks or even months. 

This is where the first benefit of serverless comes in, IaaS means you can provision infrastructure in minutes, if not seconds. Now arguably you can do this with virtual servers and even bare metal, but the real benefit is the runtime. With the cloud, you pay-as-you-go (PAYG) or as you consume. With virtual servers and bare metal, you pay from the second it starts until you stop it, which sounds fair enough. Except, you’re not using it most of the time. <a href="https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/whitepaper/solutions/business-case-for-virtualization-white-paper.pdf">VMware estimates utilization rates of between 5 – 15% for bare metal and up to 60 – 80% for virtualized</a>. So, at best, 20% of your resources are going to waste and that’s assuming your virtual servers are actually doing work 24/7.

For this scenario, let’s assume we’re virtualized and we have that mythical 80% utilization, but let’s assume our web applications only gets hit 10 times a day – we don’t know when in the day it will be used and we might get an entire years’ worth of traffic in a single hour. With virtual servers – do we just scale up the resources when this happens. Does this require an outage to happen? Do we need an expensive load balancer to somehow split the load between multiple virtual servers? Can we handle this just happening, or do we need some advance warning so we can scale up first?

With serverless, for each hit, we spin up a server, execute the required logic, then destroy the server. This means for each hit, we have the most up-to-date software any sensitive data is destroy – so you can see why the security team likes serverless, but it sounds expensive. Do you know how long the entire process takes? Less than a second. The slowest part is the bit in the middle, your code. You can realistically create a production grade, scalable solution for £1 with change!! Especially when both AWS and Azure are giving the first few thousand executions for free.

Of course, serverless isn’t always the answer. There will always be a break point where virtual servers makes more sense – just like bare metal – especially if you have predictable workloads. For AWS, a t2.nano EC2 instance costs $0.0063 per Hour. The 512mb equivalate Lambda costs $0.000000834 but this is only for 100ms, when you translate it into an hourly cost its $0.030024. 
Translate that to a yearly cost and its $259.40 vs $54.43 for a EC2 instance. Unfortunately, this is all assuming you will need to execute your code, 24/7/365, it also assumes you will executing it one at a time. It also doesn’t consider any downtime for software patching or any human costs. 

In my opinion, serverless presents an interesting innovation, I’ve personally started using AWS Lambda or Azure Functions for things I would normally have a schedule job on under used virtual server. It is especially a cool time now that .NET runs on Linux, even AWS have adopted support for .NET Core on Lambda. The only word of warning I would offer to anyone about to set out on a serverless journey – setup restrictions. Setup a separate dev sandbox account. Contact support, have the number of concurrent Lambda reduced. Put billing limits in place. Use a prepaid debit card. With the cloud, if you want a server with over 3TB of ram? Sure, AWS will give you a server with over 3TB. The only limit is your credit card. 

With cloud, AWS especially, you pay for everything. 
- You want to store something? That’s gonna cost. 
- You want to upload that data? That’s gonna cost. 
- You want to download that data from store? That’s gonna cost.
- You want to download that data outside of AWS? That’s gonna cost.
- You want a API gateway to invoke your Lambda? That’s gonna cost.
- You want to execute that Lambda function? Guess what, that’s gonna cost.

Fine, its dirt cheap, but as the saying goes, "look after the pennies and the pounds will look after themselves".
