---
title: 'sensor checks for crowdstrike'
author: ulysses

date: 2020-11-11
slug: sensor-checks-for-crowdstrike
draft: false
---

Here’s the Crowdstrike Falcon Sensor checks.

```
#!/bin/bash
if [ -e /etc/redhat-release ] ; then
  if egrep -q 'Ootpa|CentOS Linux release 8' /etc/redhat-release ; then
    OSver="el8"
  elif egrep -q 'Maipo|CentOS Linux release 7' /etc/redhat-release ; then
    OSver="el7"
  elif egrep -q 'Santiago|CentOS release 6' /etc/redhat-release ; then
    OSver="el6"
  fi
fi
if [ -e /etc/os-release ] ; then
  if grep VERSION /etc/os-release | grep -q 15 ; then
    OSver="suse15"
  elif grep VERSION /etc/os-release | grep -q 12 ; then
    OSver="suse12"
  elif grep VERSION /etc/os-release | grep -q 11 ; then
    OSver="suse11"
  elif grep -q 'Linux 2' /etc/os-release ; then
    OSver="amzn2"
  elif grep -q 'AMI' /etc/os-release ; then
    OSver="amzn1"
  fi
fi
if [[ -f "/opt/CrowdStrike/falconctl" ]]; then
  case $OSver in
    suse15)
      if [ -z "$(ss -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if systemctl is-active --quiet falcon-sensor; then status="Running"; else status="Stopped"; fi  
      ;;
    suse12)
      if [ -z "$(ss -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if systemctl is-active --quiet falcon-sensor; then status="Running"; else status="Stopped"; fi  
      ;;
    suse11)
      if [ -z "$(ss -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if (( $(ps -ef | grep -v grep | grep falcon-sensor | wc -l) > 0 )); then status="Running"; else status="Stopped"; fi
      ;;
    el8)
      if [ -z "$(netstat -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if systemctl is-active --quiet falcon-sensor; then status="Running"; else status="Stopped"; fi
      ;;
    el7)
      if [ -z "$(netstat -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if systemctl is-active --quiet falcon-sensor; then status="Running"; else status="Stopped"; fi  
      ;;
    el6)
      if [ -z "$(netstat -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if (( $(ps -ef | grep -v grep | grep falcon-sensor | wc -l) > 0 )); then status="Running"; else status="Stopped"; fi  
      ;;
    amzn2)
      if [ -z "$(netstat -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if systemctl is-active --quiet falcon-sensor; then status="Running"; else status="Stopped"; fi  
      ;;
    amzn1)
      if [ -z "$(netstat -tapn | grep falcon)" ]; then message="Not Connected"; else message="Connected"; fi
      if (( $(ps -ef | grep -v grep | grep falcon-sensor | wc -l) > 0 )); then status="Running"; else status="Stopped"; fi
      ;;
    *)
      ;;
  esac
else
    message="Not installed"
fi
if [[ -f "/opt/CrowdStrike/falconctl" ]]; then
    version=$(/opt/CrowdStrike/falconctl -g --version | awk '{print $3}')
else
    version="Not installed"
fi
if [ "$version" == "Not installed" ]; then status="Not installed"; fi
echo $version '|' $status '|' $message
```