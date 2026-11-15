---
title: 'gcp spot instance'
author: ulysses

date: 2021-11-25
slug: gcp-spot-instance
draft: false
---

You can save anywhere from 60-91% using a spot instance. The downside is, the instance can be preempted anytime.

Create a spot instance.

```
gcloud beta compute instances create spot-example \
--provisioning-model=SPOT \
--instance-termination-action=STOP \
--image-project=ubuntu-os-cloud \
--image-family=ubuntu-2004-lts \
--machine-type=e2-micro \
--project=your-project-id \
--zone=us-central1-a
```

Delete instance.

```
gcloud compute instances delete spot-example \
--project=your-project-id \
--zone=us-central1-a
```