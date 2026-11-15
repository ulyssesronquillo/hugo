---
title: 'gcp instance scopes'
author: ulysses

date: 2019-03-15
slug: gcp-instance-scopes
draft: false
---

Give Instances access to other cloud services using scopes.

```
gcloud alpha compute instances set-scopes instance-name \
--project project-name --zone us-central1-a \
--scopes=cloud-platform,cloud-source-repos,compute-rw,storage-rw
```