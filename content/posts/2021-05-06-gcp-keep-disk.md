---
title: 'gcp keep disk'
author: ulysses

date: 2021-05-06
slug: gcp-keep-disk
draft: false
---

Keep your disks when a VM is deleted.

```
gcloud compute instances set-disk-auto-delete server --no-auto-delete --disk=server-disk-1
gcloud compute instances set-disk-auto-delete server --no-auto-delete --disk=server-disk-2
```

To delete.

```
gcloud compute instances set-disk-auto-delete server --auto-delete --disk=server-disk-1
gcloud compute instances set-disk-auto-delete server --auto-delete --disk=server-disk-2
```