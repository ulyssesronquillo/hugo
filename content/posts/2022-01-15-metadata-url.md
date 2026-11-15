---
title: 'metadata url'
author: ulysses

date: 2022-01-15
slug: metadata-url
draft: false
---

Here’s the metadata URLs for both AWS and GCP.

```
curl http://169.254.169.254/computeMetadata/v1/ -H "Metadata-Flavor: Google"
curl http://169.254.169.254/latest/meta-data/
```