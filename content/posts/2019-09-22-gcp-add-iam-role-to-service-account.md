---
title: 'gcp add iam role to service account'
author: ulysses

date: 2019-09-22
slug: gcp-add-iam-role-to-service-account
draft: false
---

Here’s how to add an IAM role to a GCP Service Account.

```
gcloud projects add-iam-policy-binding your-project-id \
--member serviceAccount:service-account-name@your-project-id.iam.gserviceaccount.com \
--role roles/storage.objectAdmin
```