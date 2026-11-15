---
title: 'ipinfo.io map'
author: ulysses

date: 2021-04-24
slug: ipinfo-io-map
draft: false
---

Generate a map of your live streaming viewers by placing of your viewer’s IP into a file and then using IPInfo’s map tool.

```
vim ipList
54.0.0.1
54.0.0.2
54.0.0.3
```

To plot the IPs on a map, pipe them to IPinfo.io.

```
cat ipList | curl -XPOST --data-binary @- "ipinfo.io/map?cli=1"
```

The result is a URL of the map.