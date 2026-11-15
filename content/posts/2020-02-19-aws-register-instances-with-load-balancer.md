---
title: 'aws register instances with load balancer'
author: ulysses

date: 2020-02-19
slug: aws-register-instances-with-load-balancer
draft: false
---

Here’s the AWS CLI to register instances to a load balancer.

```
aws elb register-instances-with-load-balancer \
--load-balancer-name my-load-balancer \
--instances i-xxxxxxxxxxx i-xxxxxxxxxxx i-xxxxxxxxxxx 
```