---
title: 'gcp check instances running'
author: ulysses

date: 2020-01-18
slug: gcp-check-instances-running
draft: false
---

Here’s how to check if instances are running in GCP.

```
#!/bin/bash
while IFS=', ' read -r a b c; do
  instance="${a//[[:blank:]]/}"
  project="${b//[[:blank:]]/}"
  zone="${c//[[:blank:]]/}"
  gcloud compute instances describe $instance \
  --zone $zone --project $project \
  --format='table[no-heading](name,status,zone)'
done 
```

Instances are read from an external file. File is comma delimited with instance name, project id and zone data.