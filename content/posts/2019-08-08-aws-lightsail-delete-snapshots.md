---
title: 'aws lightsail delete snapshots'
author: ulysses

date: 2019-08-08
slug: aws-lightsail-delete-snapshots
draft: false
---

Here’s my script to delete AWS LightSail snapshots. It can delete daily or weekly backups and scheduled via crontab. If you want longer or shorter retention, adjust the expired value. It’s in seconds. 604800 is 1 week. 2592000 is 1 month.

```
#!/bin/bash

current=$(date +%s)

if [ $# -eq 0 ]; then
  exit 1
fi

if [[ $1 = 'daily' ]]; then
  prefix='daily'
  expired=$(($current-604800))
elif [[ $1 = 'weekly' ]]; then
  prefix='weekly'
  expired=$(($current-2592000))
else
  exit 1
fi

snaps='/root/snapshots/snapshots.json'
names='/root/snapshots/names.txt'
parse='/root/snapshots/parse.txt'
logfile='/root/snapshots/snapshots.log'

/usr/local/bin/aws lightsail get-instance-snapshots > $snaps
cat $snaps | jq -r '.instanceSnapshots[] | .name' > $names
cat $names | grep $prefix > $parse

while read -r line; do

  snapshot=$(echo $line | cut -d_ -f3)
  snapshotname=$line

  if [ `expr $snapshot + 1 2> /dev/null` ] ; then

    if [ $snapshot -le $expired ]; then
      echo 'Deleted: '$snapshotname >> $logfile
      /usr/local/bin/aws lightsail delete-instance-snapshot \
      --instance-snapshot-name $snapshotname
    else
      echo 'Nothing: '$snapshotname >> $logfile
    fi

  else
    echo $snapshot is not numeric > /dev/null
  fi

done > $logfile
echo 'Expired time: '$expired >> $logfile
echo '-----------------------------------' >> $logfile
```

Schedule deletes via crontab.

```
# run daily at 5am
0 5 * * * /bin/bash /root/snapshots/delete-snapshot.sh daily 2>&1
# run weekly every sunday at 6am
0 6 * * 0 /bin/bash /root/snapshots/delete-snapshot.sh weekly 2>&1
```