---
title: 'waf cloudformation template'
author: ulysses

date: 2020-04-21
slug: waf-cloudformation-template
draft: false
---

Here’s the [CloudFormation template](https://docs.aws.amazon.com/solutions/latest/aws-waf-security-automations/template.html) for creating a WAF.

Here are some options that you’ll be asked during creation.

- Activate SQL Injection Protection ( yes | no )
- Activate Cross-site Scripting Protection ( yes | no )
- Activate HTTP Flood Protection ( WAF rate | Lambda log parser | Athena log parser | no )
- Activate Scanner &amp; Probe Protection ( Lambda log parser | Athena log parser | no )
- Activate Reputation List Protection ( yes | no )
- Activate Bad Bot Protection ( yes | no )
- Endpoint Type (CloudFront or ALB)
- Application Access Log Bucket Name ( Leave blank if no S3 bucket)

The template creates 2 CloudFormation stacks.