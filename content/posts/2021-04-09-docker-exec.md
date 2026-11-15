---
title: 'docker exec'
author: ulysses

date: 2021-04-09
slug: docker-exec
draft: false
---

If you want to SSH to a Docker container, use the Docker exec command.

```
docker exec -it container_name bash
docker exec -it --user root container_name /bin/bash
```

I’m using a Git Bash terminal, so I have to prefix the docker command with winpty.

```
winpty docker exec -it container_name bash
```

Result

```
root@681bbe3f65f1:/var/www/html#
```

Ctrl-D to exit.
