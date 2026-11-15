---
title: 'gcp instance scheduler'
author: ulysses

date: 2021-05-28
slug: gcp-instance-scheduler
draft: false
---

GCP recently added Instance Schedule to its console.

To configure, perform the following.

– Create an instance schedule.  
– Add instance(s) to a schedule.  
– If no errors, the service account has the correct permissions.

The service account used by Instance Schedule is owned by GCP and is not visible in the GCP console.

If service account has no permissions, the you must perform the following.

– Create a custom role with compute.instances.start and compute.instances.stop permissions.  
– Add custom role to the service account.

Finally, validate instances are starting and stopping based on schedule.