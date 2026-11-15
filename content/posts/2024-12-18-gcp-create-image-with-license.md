---
author: ulysses
title: 'gcp create image with license'
date: 2024-12-18
slug: gcp-create-image-with-license
draft: false
---

Here's the gcloud command to create a new image with an extended license with an option to add family type.

```
gcloud beta compute images create new-image-with-license \
--source-image=this-is-the-source-image \
--family rocky-9 \
--project your-project-id \
--user-licenses=https://www.googleapis.com/compute/v1/projects/rhel-cloud/global/licenses/rhel-7-els
```

Any VM provisioned using this image will now have the extended license.

