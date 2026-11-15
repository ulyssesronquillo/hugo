---
title: 'gcp listing reservations'
author: ulysses

date: 2020-09-21
slug: gcp-listing-reservations
draft: false
---

Here’s how to list reservations in GCP.

```
gcloud compute reservations list --project project-id
```

Specify a zone.

```
gcloud compute reservations list \
--filter="zone:('us-central1-a')" \
--project project-id
```