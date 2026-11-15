---
title: 'icecast on docker'
author: ulysses

date: 2019-07-05
slug: icecast-on-docker
draft: false
---

Run Icecast2 on a Docker container.

```
docker run -d \
-p 8000:8000 \
-e ICECAST_SOURCE_PASSWORD=aaaa \
-e ICECAST_ADMIN_PASSWORD=bbbb \
-e ICECAST_PASSWORD=cccc \
-e ICECAST_RELAY_PASSWORD=dddd \
moul/icecast
```

Access localhost:8000 on browser. [Github](https://github.com/moul/docker-icecast).