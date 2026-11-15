---
title: 'splunk search for tanium clients'
author: ulysses

date: 2020-02-24
slug: splunk-search-for-tanium-clients
draft: false
---

Here’s the Splunk search for Tanium clients reporting to the Tanium server.

```
"data.jsonPayload.rule_details.direction"=EGRESS
"data.jsonPayload.connection.src_ip"="10.0.0.1"
"data.jsonPayload.connection.dest_port"=17472
```