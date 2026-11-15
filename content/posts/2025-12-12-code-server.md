---
author: ulysses
title: 'code server'
date: 2025-12-12
slug: code-server
draft: false
---
Code-server runs Visual Studio Code (VS Code) on a remote server making it accessible via a web browser.

I use docker-compose to host code-server on a container.

Here's my docker-compose.yml.

```
services:
  code-server:
    image: lscr.io/linuxserver/code-server:latest
    container_name: code-server
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
      - PASSWORD=xxxxxxxx                   #optional
      - HASHED_PASSWORD=                    #optional
      - SUDO_PASSWORD=xxxxxxxx              #optional
      - SUDO_PASSWORD_HASH=                 #optional
      - PROXY_DOMAIN=code-server.my.domain  #optional
      - DEFAULT_WORKSPACE=/config/workspace #optional
      - PWA_APPNAME=code-server             #optional
    volumes:
      - /home/ulysses/Code:/config
    ports:
      - 8443:8443
    restart: unless-stopped
```

There are a few things that are optional and can be skipped.

Bring it up.

```
docker-compose up -d
```

Access the code-server from a browser. 

```
http://localhost:8443
# OR
http://192.168.168.10:8443
```

It looks just like VSCode, but only in the browser.

If you're done, just bring it down.

```
docker-compose down
```

That is all.