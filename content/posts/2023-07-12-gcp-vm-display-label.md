---
title: 'gcp vm display label'
author: ulysses

date: 2023-07-12
slug: gcp-vm-display-label
draft: false
---

Here’s how to display GCP VM labels.

Display all labels.

```
gcloud compute instances describe VM --zone ZONE --project PROJECT_ID --format="value(labels)"
```

Display a specific label.

```
gcloud compute instances describe VM --zone ZONE --project PROJECT_ID --format="value(labels.key)"
```