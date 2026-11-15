---
title: 'gcp create service account'
author: ulysses

date: 2019-09-22
slug: gcp-create-service-account
draft: false
---

Here’s how to create a GCP Service Account.

```
gcloud beta iam service-accounts create service-account-name \
    --description "service account description" \
    --display-name "service account display name"
```