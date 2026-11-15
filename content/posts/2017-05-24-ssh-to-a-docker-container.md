---
title: 'ssh to a docker container'
author: ulysses

date: 2017-05-24
slug: ssh-to-a-docker-container
draft: false
---

Docker containers are awesome. Docker allows you to quickly create development environments in a matter of minutes. Docker gives you the ability to package, ship and share your docker image to anyone. Once your docker image is on the Docker repository, anyone can pull it down and run it on their own operating system.

To keep track of running containers on your system, you can type ‘docker ps -a’ on your terminal.

```
$ docker ps -a
# gives a result similar to this ...
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                    NAMES
f322d2370415        moul/icecast        "/start.sh"              2 hours ago         Up 2 hours          0.0.0.0:8000->8000/tcp   icecast_icecast_1
```

If you would like to SSH to a running Docker container, just run the following from the terminal.

```
docker exec -t -i f322d2370415 /bin/bash
# it will take you to this ... 
root@f322d2370415:/#
```

f322d2370415 is the Container ID, while /bin/bash is the shell that you would like to use.