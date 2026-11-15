---
title: 'troubleshoot nameservers with dig'
author: ulysses

date: 2021-04-08
slug: troubleshoot-nameservers-with-dig
draft: false
---

Here’s how to troubleshoot nameservers with dig.

```
dig hostname
dig domain.com
```

To test a specific nameserver.

```
dig @nameserver hostname
dig @nameserver ip-address
```

Other options.

```
dig hostname.domain.com +short
dig hostname.domain.com +noall +answer
dig @nameserver MX domain.com
dig @nameserver AAAA domain.com
```