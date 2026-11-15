---
title: 'gcp create service account key'
author: ulysses

date: 2019-09-22
slug: gcp-create-service-account-key
draft: false
---

Here’s how to create a key for the GCP Service Account.

Create Key.

```
gcloud iam service-accounts keys create ~/key.json \
  --iam-account service-name@project-id.iam.gserviceaccount.com
```

Activate Key

```
gcloud auth activate-service-account service-name@project-id.iam.gserviceaccount.com \
--key-file=key.json
```

Revoke Key.

```
gcloud auth revoke service-account@project-id.iam.gserviceaccount.com
```

Delete Key

```
gcloud iam service-accounts keys delete key-id \
    --iam-account service-name@project-id.iam.gserviceaccount.com
```