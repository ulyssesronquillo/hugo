---
title: 'active ssl and tls protocols'
author: ulysses

date: 2023-09-15
slug: active-ssl-and-tls-protocols
draft: false
---

Here’s the command to list what SSL and TLS protocols are active.

```
openssl ciphers -v | awk '{print $2}' | sort | uniq
```