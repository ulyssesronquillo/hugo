---
title: 'gcp list keys of service account'
author: ulysses

date: 2022-01-26
slug: gcp-list-keys-of-service-account
draft: false
---

How to list all the keys of a GCP service account.

```
gcloud iam service-accounts keys list \
--iam-account=your-service-account@your-project-id.iam.gserviceaccount.com \
--project project-id
```

Result. Keys are redacted.

```
KEY_ID                                    CREATED_AT            EXPIRES_AT            DISABLED
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  2022-01-10T19:21:18Z  2022-01-26T19:21:18Z
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  2022-01-19T00:06:49Z  2022-02-04T00:06:49Z
```