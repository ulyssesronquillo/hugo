---
title: 'checking what ssl and tls are in use'
author: ulysses

date: 2023-09-15
slug: checking-what-ssl-and-tls-are-in-use
draft: false
---

Here’s another command to check what version of SSL and TLS is being used.

```
nmap --script ssl-enum-ciphers -p 443 server.domain.com
```

Result

```
PORT    STATE SERVICE
443/tcp open  https
| ssl-enum-ciphers: 
|   TLSv1.2: 
|     ciphers:
...
```

In this example, only TLSv1.2 is in use. For security purposes, use TLSv1.2 or higher.