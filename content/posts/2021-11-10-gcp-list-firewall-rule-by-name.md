---
title: 'gcp list firewall rule by name'
author: ulysses

date: 2021-11-10
slug: gcp-list-firewall-rule-by-name
draft: false
---

Here’s how to list a GCP firewall rule by name.

```
gcloud compute firewall-rules list \
--filter="name=('wowza-rtmp')" \
--format=json
```

You can use different formats. Supported formats are:

config, csv, default, diff, disable, flattened, get, json, list, multi, none, object, table, text, value, yaml