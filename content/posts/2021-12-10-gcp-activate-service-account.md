---
title: 'gcp activate service account'
author: ulysses

date: 2021-12-10
slug: gcp-activate-service-account
draft: false
---

How to activate a GCP service account for other users in Linux.

First generate a key for the service account. Save as key.json.

Login to the server as that user and copy the key there. Activate the service account.

```
$ gcloud auth activate-service-account [ACCOUNT] --key-file=key.json
```

Once authenticated, you should be able to check if service account is active.

```
$ gcloud config list
```

A better option without needing a key.

```
gcloud config set core/account service-account@project-id.iam.gserviceaccount.com
```