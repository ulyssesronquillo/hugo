---
title: 'gcp gcloud compute scp'
author: ulysses

date: 2022-01-31
slug: gcp-gcloud-compute-scp
draft: false
---

Here’s how to download/upload files using gcloud compute scp.

Make sure you are authenticated.

```
gcloud auth login
```

How to download.

```
gcloud compute scp --recurse your-server:/home/username/yaml.tar.gz . \
--project your-project-id \
--zone us-central1-a \
--internal-ip
```

How to upload.

```
gcloud compute scp --recurse yaml.tar.gz your-server:/home/username/ \
--project your-project-id \
--zone us-central1-a \
--internal-ip
```