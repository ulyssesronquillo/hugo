---
title: 'gcp windows password reset'
author: ulysses

date: 2022-02-14
slug: gcp-windows-password-reset
draft: false
---

Instead of the GCP Console, you can reset Windows Server password via gcloud.

```
gcloud compute reset-windows-password server-name \
--zone us-central1-a \
--project project-id
```

Username and password will generated.