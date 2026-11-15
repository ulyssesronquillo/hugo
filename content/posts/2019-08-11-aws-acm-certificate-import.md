---
title: 'aws acm certificate import'
author: ulysses

date: 2019-08-11
slug: aws-acm-certificate-import
draft: false
---

Here’s how to import a SSL certificate into AWS Certificate Manager.

 ```
aws acm import-certificate \
--certificate fileb://example.crt \
--private-key fileb://example.key \
--certificate-chain fileb://example-bundle.crt \
--tags Key=Name,Value=mydomain.com_20220107
```