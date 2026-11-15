---
title: 'gcp monitor service account'
author: ulysses

date: 2022-02-24
slug: gcp-monitor-service-account
draft: false
---

You can monitor the success or failure of a service account in GCP.

```
gcloud policy-intelligence query-activity \
--activity-type=ACTIVITY_TYPE \ 
--project=PROJECT_ID \
--limit=LIMIT
```

The two options you can use for ACTIVITY\_TYPE are:

- serviceAccountKeyLastAuthentication
- serviceAccountLastAuthentication