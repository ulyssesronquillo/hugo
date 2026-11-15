---
title: 'docker to gcr'
author: ulysses

date: 2020-01-12
slug: docker-to-gcr
draft: false
---

Here’s a couple of steps to move a Docker image to the Google Container Registry.

Create a container image.

```
docker build -t gcr.io/${PROJECT_ID}/my-app:v1 .
```

Push image to GCR.

```
docker push gcr.io/[PROJECT-ID]/[IMAGE]
```