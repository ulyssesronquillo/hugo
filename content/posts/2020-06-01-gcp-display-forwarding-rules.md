---
title: 'gcp display forwarding rules'
author: ulysses

date: 2020-06-01
slug: gcp-display-forwarding-rules
draft: false
---

Here’s how to display a list of Google Cloud forwarding rules.

```
gcloud compute forwarding-rules list
```

If you want global only.

```
gcloud compute forwarding-rules --global
```

Or just local regions only.

```
gcloud compute forwarding-rules --filter="region:( us-central us-west1 )"
```