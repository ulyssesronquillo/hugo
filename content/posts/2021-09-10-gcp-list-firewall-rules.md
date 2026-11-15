---
title: 'gcp list firewall rules'
author: ulysses

date: 2021-09-10
slug: gcp-list-firewall-rules
draft: false
---

Here’s how to list GCP firewall rules while filtering a service account. Output is exported as a CSV file.

```
gcloud compute firewall-rules list \
--project host-project \
--filter=service-account-name \
--format="csv(
name,
network,
direction,
priority,
sourceRanges.list():label=SRC_RANGES,
destinationRanges.list():label=DEST_RANGES,
allowed[].map().firewall_rule().list():label=ALLOW,
denied[].map().firewall_rule().list():label=DENY,
sourceTags.list():label=SRC_TAGS,
sourceServiceAccounts.list():label=SRC_SVC_ACCT,
targetTags.list():label=TARGET_TAGS,
targetServiceAccounts.list():label=TARGET_SVC_ACCT,
disabled)" \
> export.csv
```