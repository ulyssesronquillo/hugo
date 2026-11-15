---
title: 'capture gcp vm serial port output to terminal'
author: ulysses

date: 2023-08-28
slug: capture-gcp-vm-serial-port-output-to-terminal
draft: false
---

Here’s the command to capture a GCP VM serial port output to your terminal.

```
gcloud compute instances get-serial-port-output servername \
--zone us-central1-f \
--project your-project \
--port 1 
```

You can also send the output to a file.

```
gcloud compute instances get-serial-port-output servername \
--zone us-central1-f \
--project your-project \
--port 1 > output.txt
```