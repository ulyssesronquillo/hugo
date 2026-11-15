---
title: 'gcp fix hosts'
author: ulysses

date: 2021-12-07
slug: gcp-fix-hosts
draft: false
---

This is a script that fixes /etc/hosts in GCP.

```
#!/bin/bash

# VARIABLES
FILE='/etc/hosts'

#BACKUP /etc/hosts before changes
cp -ipHR $FILE $FILE_$(date +%Y-%m-%d_%H-%M-%S)

# GET IP ADDRESS
IP=$(/sbin/ifconfig | grep 'inet' | grep -v 'inet6' | grep -v '127.0' | cut -d: -f2 | awk '{print $2}' | head -1)

# GET HOSTNAME
HN=$(/bin/hostname)

# GET PROJECT ID
echo "169.254.169.254 metadata.google.internal  # Added by Google" >> $FILE
PR=$(curl -f -s http://metadata.google.internal/computeMetadata/v1/project/project-id -H "Metadata-Flavor: Google")

# ADD HOSTNAME ENTRY TO /etc/hosts
STRING="$IP $HN.mydomain.com"

if grep -q "$STRING" "$FILE"
then
  echo "Valid host entry."
else
  echo "Adding host entry."
  echo $STRING $HN >> $FILE
fi

# DELETE GOOGLE ENTRIES.
sed -i '/# Added by Google/d' $FILE

# ADD BACK GOOGLE ENTRIES.
echo $IP $HN".c."$PR".internal" $HN"  # Added by Google" >> $FILE
echo "169.254.169.254 metadata.google.internal  # Added by Google" >> $FILE

# SET PERMISSIONS.
chmod 644 $FILE

# DISPLAY /etc/hosts
cat $FILE
```

Result

```
127.0.0.1       localhost
::1             localhost ip6-localhost ip6-loopback
ff02::1         ip6-allnodes
ff02::2         ip6-allrouters

10.128.0.30 test.mydomain.com test
10.128.0.30 test.c.project-id.internal test  # Added by Google
169.254.169.254 metadata.google.internal  # Added by Google
```

It adds a proper host entry before the Google entries. /etc/hosts has top to bottom precedence.