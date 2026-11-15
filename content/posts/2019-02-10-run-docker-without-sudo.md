---
title: 'run docker without sudo'
author: ulysses

date: 2019-02-10
slug: run-docker-without-sudo
draft: false
---

Run Docker without sudo. Add user to docker group. Login as docker using newgrp.

```
sudo gpasswd -a $user docker
newgrp docker
```

You can now run the following commands without sudo.

```
docker ps
docker images
```

Every time you open a new terminal , just run.

```
newgrp docker
```