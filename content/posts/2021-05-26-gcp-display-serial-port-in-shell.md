---
title: 'gcp display serial port in shell'
author: ulysses

date: 2021-05-26
slug: gcp-display-serial-port-in-shell
draft: false
---

How to display serial port in GCP Cloud Shell.

```
gcloud compute instances get-serial-port-output instance-name \
--zone=us-central1-a \
--project=your-project-id
```