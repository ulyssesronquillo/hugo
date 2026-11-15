---
title: 'parsing wowza logs'
author: ulysses

date: 2019-03-19
slug: parsing-wowza-logs
draft: false
---

I’ve been wanting to look at Wowza logs for a very long time. I just spent a couple of hours writing a Bash script that generates a stats report. It parses the Wowza log file for the IP addresses, and runs them and against a site called ipinfo.io to get the viewer’s geo location. The output is filtered, sorted, takes a count, and finally generates a webpage. Here’s the Bash script.

```
# Can be placed in cron to run.
create-wowza-report.sh wowzastreamingengine_access.log
```

```
#!/bin/bash

# check for missing argument
if [ -z "$1" ]
  then
    echo "No arguments supplied. Format: create-wowza-report.sh wowzastreamingengine_access.log"
    exit 1
fi

# get the ips from the wowza log file
awk '{print $17}' $1 > output1.txt

# exclude invalid ips 
grep '[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}\.[0-9]\{1,3\}' output1.txt > output2.txt

# sort unique ips
cat output2.txt | sort -u | uniq > ips.txt

# pause for 1s
sleep 1s

# empty file just in case
> output3.txt

# set filename
filename="ips.txt"

# read filename and get geo info
while read -r ipaddress; do
  curl ipinfo.io/"$ipaddress" 2>/dev/null | awk -F'"' '$2=="city"{printf("%s, ", $4)}$2=="region"{print $4}' >> output3.txt
done  output4.txt

# sort output alphabetically
cat output4.txt | sort > output5.txt

# get a count of connections
count=$(wc -l  $filename.php

<title>Wowza Streaming Stats on $date</title>

<h1>Live Streaming Stats</h1>
<?php include('$filename.txt');??>

EOF

# move files to web directory
cp $filename.* /var/www/html

# cleanup files
rm output*.txt
rm ips.txt
```