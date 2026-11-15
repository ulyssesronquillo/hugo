---
author: ulysses
title: 'supportconfig options'
date: 2024-02-06
slug: supportconfig-options
draft: false
---

I ran supportconfig on a system the other day and it took all night. I gave up and killed it. 

So, here are a few options that you can try to speed things up.

```
supportconfig -o OFILES,CRASH,FILES,PROC,NFS,LDAP,SSSD
```
Hope that helps.
