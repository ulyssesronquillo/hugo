---
title: 'gcp create cud reservations'
author: ulysses

date: 2020-09-13
slug: gcp-create-cud-reservations
draft: false
---

This will create a CUD (Committed Used Discounts) Reservation in GCP.

```
gcloud compute reservations create reservation-name-us-central1-a \
--machine-type=n1-standard-4 \
--vm-count=1 \
--zone=us-central1-a \
--require-specific-reservation
```

This creates a specific reservation instead of an open reservation.