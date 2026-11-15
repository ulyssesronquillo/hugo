---
title: 'aws list of application lb'
author: ulysses

date: 2020-08-17
slug: aws-list-of-application-lb
draft: false
---

Here’s how to display a list of application load balancers.

```
aws elbv2 describe-load-balancers --profile --region us-east-1
```

Here’s how to display classic load balancers.

```
aws elb describe-load-balancers --profile --region us-east-1
```