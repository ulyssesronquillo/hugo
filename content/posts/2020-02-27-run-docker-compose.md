---
title: 'run docker compose'
author: ulysses

date: 2020-02-27
slug: run-docker-compose
draft: false
---

Here’s how to run docker-compose. I have an Icecast docker-compose.yml file. Icecast is an audio streaming server.

```
version: "2"

services:
  icecast:
    image: moul/icecast
    environment:
      - ICECAST_SOURCE_PASSWORD=secret
      - ICECAST_ADMIN_PASSWORD=secret
      - ICECAST_PASSWORD=secret
      - ICECAST_RELAY_PASSWORD=secret
    ports:
      - "8000:8000"
    restart: always
```

To run Icecast in a container , I run docker-compose in the background.

```
docker-compose up -d
```

Check to see if Icecast is running on your browser.

```
http://localhost:8000
```

To stop the Icecast container, I simply stop the docker-compose.

```
docker-compose stop
```

Here are the other docker commands you can run.

```
docker images
docker ps
docker-compose ps
```