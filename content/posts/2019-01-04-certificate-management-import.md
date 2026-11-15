---
title: 'certificate management import'
author: ulysses

date: 2019-01-04
slug: certificate-management-import
draft: false
---

My previous post lightly talked about about adding SSL certificates via the AWS Console. This post talks about adding your own SSL certificate to Certificate Manager via the AWS CLI. The CLI which makes it super simple to manage. It also allows for automation as well.

 ```
aws acm import-certificate \
--certificate fileb://Certificate.pem \
--certificate-chain fileb://CertificateChain.pem \
--private-key fileb://PrivateKey.pem
```

If successful, it will return ARN or Amazon Resource Name.