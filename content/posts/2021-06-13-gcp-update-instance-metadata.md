---
title: 'gcp update instance metadata'
author: ulysses

date: 2021-06-13
slug: gcp-update-instance-metadata
draft: false
---

How to update an instance metadata in GCP.

```
gcloud compute instances add-metadata instance-name \
--metadata key-name=value \
--project your-project-id \
--zone us-central1-a
```

In this example, we are adding enable-oslogin=TRUE.

```
gcloud compute instances add-metadata instance-name \
--metadata enable-oslogin=TRUE \
--project your-project-id \
--zone us-central1-a
```