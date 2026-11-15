---
title: 'gcp set scopes'
author: ulysses

date: 2020-09-04
slug: gcp-set-scopes
draft: false
---

Here’s how to set the instance scope in GCP. Stop the server.

```
gcloud compute instances stop server-name
```

Default scopes.

```
gcloud beta compute instances set-scopes server-name \
--service-account=your-service-account@gserviceaccount.com \
--scopes=default \
--project your-project-id \
--zone=us-central1-a
```

Change scopes by adding storage-rw to default.

```
gcloud alpha compute instances set-scopes servername \
--service-account=your-service-account@gserviceaccount.com \
--scopes=default,storage-rw \
--project your-project-id \
--zone=us-central1-c
```

Start the server.

```
gcloud compute instances start server-name
```

Possible scope values.

- default
- cloud-platform
- storage-rw
- and [more](https://cloud.google.com/sdk/gcloud/reference/alpha/compute/instances/set-scopes)