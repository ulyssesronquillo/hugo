---
title: 'aws elb ssl listener'
author: ulysses

date: 2022-01-31
slug: aws-elb-ssl-listener
draft: false
---

Here’s how to update SSL certificates to AWS ELB.

Import SSL certificate

```
aws acm import-certificate \
--certificate fileb://example.crt \
--private-key fileb://example.key \
--certificate-chain fileb://example-bundle.crt \
--tags Key=Name,Value=mydomain.com_20220107 \
--profile default
```

Add SSL to a listener.

```
aws elbv2 add-listener-certificates \
--listener-arn arn:aws:elasticloadbalancing:us-east-1:xxxxxxxxxxxxx:listener/app/elbname/xxxxxxxxxxxxxxxx/xxxxxxxxxxxxxxxx \
--certificates CertificateArn=arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx \
--profile default
```

Modify listener. Set SSL certificate as default.

```
aws elbv2 modify-listener \
--listener-arn arn:aws:elasticloadbalancing:us-east-1:xxxxxxxxxxxxx:listener/app/elbname/xxxxxxxxxxxxxxxx/xxxxxxxxxxxxxxxx \
--certificates CertificateArn=arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx \
--profile default
```

Remove SSL from a listener.

```
aws elbv2 remove-listener-certificates \
--listener-arn arn:aws:elasticloadbalancing:us-east-1:xxxxxxxxxxxxx:listener/app/elbname/xxxxxxxxxxxxxxxx/xxxxxxxxxxxxxxxx \
--certificates CertificateArn=arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx \
--profile default
```