---
title: 'gcp move instance to another zone'
author: ulysses

date: 2019-12-13
slug: gcp-move-instance-to-another-zone
draft: false
---

Moving a GCP instance to another zone is actually much simpler than initially thought. It’s just a single gcloud command.

```
gcloud compute instances move instance-name \
--zone us-central1-a \
--destination-zone us-central1-b
```

A few details about moving to another zone.

- VM has to be running.
- You may get a new internal or external IP address
- Local SSDs are ephemeral, so you can’t move them.
- When moving between regions, you may have to select a subnetwork.
- You may have to change GPUs available in the destination if you use them.