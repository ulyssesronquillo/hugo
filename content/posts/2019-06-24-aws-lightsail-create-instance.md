---
title: 'aws lightsail create instance'
author: ulysses

date: 2019-06-24
slug: aws-lightsail-create-instance
draft: false
---

How to create a LightSail instance from a snapshot via AWS CLI.

```
aws lightsail create-instances-from-snapshot \
--instance-names your-server-name \
--availability-zone us-east-1a \
--instance-snapshot-name your-snapshot \
--bundle-id nano_1_0 \
--key-pair-name your-key-pair
```