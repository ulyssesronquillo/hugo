---
title: 'gcp compute enable os login'
author: ulysses

date: 2021-05-27
slug: gcp-compute-enable-os-login
draft: false
---

If you have trouble logging in (SSH) to your GCP instance, you may have to enable OS Login.

```
gcloud compute instances add-metadata server-name \
--metadata enable-oslogin=TRUE \
--zone us-central1-c \
--project project-id
```

When done, you can set it back to FALSE.