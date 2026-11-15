---
title: 'gcp list snapshots'
author: ulysses

date: 2019-06-13
slug: gcp-list-snapshots
draft: false
---

Here are several examples how to display GCP snapshots using Google SDK (CLI – command line interface).

```
# list snapshots
gcloud compute snapshots list \
--project my-project \
--filter="name~'my-server-boot'"
# limit 10
gcloud compute snapshots list \
--project my-project \
--filter="name~'my-server-boot'" \
--limit 10
# reverse order
gcloud compute snapshots list \
--project my-project \
--filter="name~'my-server-boot'" \
--limit 10 \
--sort-by="~name"
# display uri
gcloud compute snapshots list \
--project my-project \
--filter="name~'my-server-boot'" \
--limit 10 \
--sort-by="~name" \
--uri
```