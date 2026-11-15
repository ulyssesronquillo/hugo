---
title: 'gcp login service account'
author: ulysses

date: 2021-05-13
slug: gcp-login-service-account
draft: false
---

Here’s the command to authenticate as a service account.

```
gcloud auth activate-service-account --key-file=key.json
```

To log out.

```
gcloud auth revoke
```