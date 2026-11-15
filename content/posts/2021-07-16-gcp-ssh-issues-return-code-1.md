---
title: 'gcp ssh issues return code [1]'
author: ulysses

date: 2021-07-16
slug: gcp-ssh-issues-return-code-1
draft: false
---

If you are getting this return code \[1\] error, check if enable-oslogin metadata is set to TRUE in your VM.

Here’s the error when logging in.

```
gcloud compute ssh your-server-name \
--zone us-central1-a \
--project your-project-id \
--internal-ip &
ERROR: (gcloud.compute.ssh) [C:\Program Files (x86)\Google\Cloud SDK\google-cloud-sdk\bin\sdk\plink.exe] exited with return code [1].
```

Remove metadata.

```
gcloud compute instances remove-metadata your-server-name \
--keys=enable-oslogin \
--zone us-central1-a \
--project your-project-id
Updated [https://www.googleapis.com/compute/v1/projects/your-project-id/zones/us-central1-a/instances/your-server-name].
```

Run gcloud ssh again.

```
gcloud compute ssh your-server-name \
--zone us-central1-a \
--project your-project-id \
--internal-ip &
[1] 1257
```

This time it opens up a Putty session and you’re able to login.