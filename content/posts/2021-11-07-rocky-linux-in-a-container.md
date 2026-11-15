---
title: 'rocky linux in a container'
author: ulysses

date: 2021-11-07
slug: rocky-linux-in-a-container
draft: false
---

Here’s how to run Rocky Linux in a Docker container.

Download the image.

```
docker pull rockylinux/rockylinux
```

Create a Rocky Linux container called bullwinkle.

```
docker run -it --name bullwinkle -d rockylinux/rockylinux
```

Login to the container using bash.

```
docker exec -it --user root bullwinkle /bin/bash
```

When done, stop and delete the container.

```
docker ps -a
docker stop container_ID
docker rm container_ID
```