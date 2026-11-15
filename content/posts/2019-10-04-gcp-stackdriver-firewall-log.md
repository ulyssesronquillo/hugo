---
title: 'gcp stackdriver firewall log'
author: ulysses

date: 2019-10-04
slug: gcp-stackdriver-firewall-log
draft: false
---

Here’s one way how to look at traffic hitting a GCP firewall. To view the traffic activity, go to Stackdriver Logging &gt; Viewer. Enter the following search string. Just replace the network name and firewall name.

```
logName:(projects/project-name/logs/compute.googleapis.com%2Ffirewall) 
AND jsonPayload.rule_details.reference:("network:network-name/firewall:firewall-name")
```