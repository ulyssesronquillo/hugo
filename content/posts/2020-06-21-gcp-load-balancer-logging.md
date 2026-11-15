---
title: 'gcp load balancer logging'
author: ulysses

date: 2020-06-21
slug: gcp-load-balancer-logging
draft: false
---

Go to Logging &gt; Logs Viewer to monitor a GCP Load Balancer.

```
resource.type="http_load_balancer" AND resource.labels.url_map_name="your-lb" AND resource.labels.project_id="your-project-id"
```