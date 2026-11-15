---
title: 'ssl certificates explained'
author: ulysses

date: 2019-01-20
slug: ssl-certificates-explained
draft: false
---

If you’re confused about the different formats and files that the Certificate Manager will accept in AWS, this [site](https://helpdesk.ssls.com/hc/en-us/articles/115001391705-How-to-install-a-SSL-certificate-on-AWS) explains it fairly well. The Certificate Manager contains 3 fields during the import process. Certificate body, Certificate private key, and Certificate chain.

![](https://uly.me/wp-content/uploads/2019/01/cm.png)

Server certificate &gt; Intermediate certificate &gt; Root certificate
- Private RSA Key
- Chain consists of Root and Intermediate