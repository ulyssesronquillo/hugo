---
title: 'gcp list instances with service account'
author: ulysses

date: 2020-09-23
slug: gcp-list-instances-with-service-account
draft: false
---

Here’s how to list GCP instances with a specific service account.

```
gcloud compute instances list \
--project your-project-id \
--format="value(name,serviceAccounts[].email)" \
--filter="serviceAccounts.email=your-service-account@email.com AND name~\bwp"
```

I’m using filters to look for a specific service account, and any instance starting with ‘wp.’ \\b means begins with.