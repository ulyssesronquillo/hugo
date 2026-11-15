---
title: 'aws update acm certs'
author: ulysses

date: 2020-10-04
slug: aws-update-acm-certs
draft: false
---

Here’s how to update AWS Certificate Manager SSL Cert.

```
#!/bin/bash
cd /etc/letsencrypt/live/domain.com/

arn='arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'

aws acm import-certificate \
--certificate fileb://cert.pem \
--certificate-chain fileb://chain.pem \
--private-key fileb://privkey.pem \
--certificate-arn $arn \
--region us-east-1
```

You can run this every time certbot updates your certificate. Or you can schedule it in crontab.