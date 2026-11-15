---
title: 'what requires openssl'
author: ulysses

date: 2023-09-15
slug: what-requires-openssl
draft: false
---

Here’s the command to list what app or package requires OpenSSL.

```
repoquery --whatrequires --installed --recursive openssl
```

Result

```
authconfig-0:6.2.8-30.el7.x86_64
falcon-sensor-0:6.38.0-13501.el7.x86_64
python2-cryptography-0:1.7.2-2.el7.x86_64
realmd-0:0.16.1-12.el7_9.1.x86_64
terraform-0:1.3.6-1.x86_64
```