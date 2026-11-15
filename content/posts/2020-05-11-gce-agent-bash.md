---
title: 'gce agent bash'
author: ulysses

date: 2020-05-11
slug: gce-agent-bash
draft: false
---

This is a Bash script to restart a service.

```
#!/bin/bash

SERVICE=google_osconfig_agent
AGENT=google-osconfig-agent

if (( $(ps -ef | grep -v grep | grep $SERVICE | wc -l) > 0 ))
then
    echo "$AGENT service running, everything is fine"
else
    echo "$AGENT is not running"
    echo "Restarting service"
    systemctl start $AGENT
    sleep 5s
    if (( $(ps -ef | grep -v grep | grep $SERVICE | wc -l) > 0 ))
    then
      sleep 2s
      echo "$AGENT service is now running"
    fi
fi
```