---
title: 'gcp disks attach to an instance'
author: ulysses

date: 2020-09-15
slug: gcp-disks-attach-to-an-instance
draft: false
---

Here’s how to display a list the disks attached to an instance.

```
gcloud compute instances describe instance-name \
--project project-id \
--zone us-central1-c \
--format='yaml(disks[].source)'
```