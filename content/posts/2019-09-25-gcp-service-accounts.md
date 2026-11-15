---
title: 'gcp service accounts'
author: ulysses

date: 2019-09-25
slug: gcp-service-accounts
draft: false
---

Here’s how display the Service Account of a particular instance in Google Cloud.

```
gcloud compute instances describe server-name \
--zone us-central1-c \
--project project-id \
--format="flattened(serviceAccounts[].email)"
```

Result is:

```
serviceAccounts[0].email: service-account-name@project-id.iam.gserviceaccount.com
```