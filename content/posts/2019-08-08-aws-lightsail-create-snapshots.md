---
title: 'aws lightsail create snapshots'
author: ulysses

date: 2019-08-08
slug: aws-lightsail-create-snapshots
draft: false
---

Here’s my script to create snapshots of a LightSail instance. Create daily or weekly snapshots.

```
#!/bin/bash
if [ $1 != '' ]; then 
  prefix=$1
  timestamp=$(date +%s)
  snapshotname=$prefix'_web-server_'$timestamp
  /usr/local/bin/aws lightsail create-instance-snapshot \
  --instance-snapshot-name $snapshotname \
  --instance-name web-server
else
  echo 'Need one argument. e.g. daily or weekly'
fi
```

Crontab. Job can be scheduled daily or weekly.

```
# run daily at 4am
0 4 * * * /bin/bash /root/snapshots/create-snapshot.sh daily 2>&1
# run weekly every sunday at 5am
0 5 * * 0 /bin/bash /root/snapshots/create-snapshot.sh weekly 2>&1
```