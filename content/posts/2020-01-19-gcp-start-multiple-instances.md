---
title: 'gcp start multiple instances'
author: ulysses

date: 2020-01-19
slug: gcp-start-multiple-instances
draft: false
---

Here’s how to start multiple instances using Bash and Google SDK.

```
#!/bin/bash
while IFS=', ' read -r a b c; do
  instance="${a//[[:blank:]]/}"
  project="${b//[[:blank:]]/}"
  zone="${c//[[:blank:]]/}"
  echo "Starting $instance ...."
  gcloud compute instances start $instance \
  --zone $zone --project $project --async
done 
```

Instances are read from an external file. The file format is displayed below.


```
server1,project1,us-central1-a
server2,project2,us-central1-b
server3,project3,us-central1-c
```

To stop multiple instances, replace "start" with "stop."