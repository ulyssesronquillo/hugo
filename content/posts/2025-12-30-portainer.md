---
author: ulysses
title: 'portainer'
date: 2025-12-30
slug: portainer
draft: false
---
Portainer is an enterpise container management platform to deploy, troubleshoot and secure Kubernetes, Docker and Podman environments.

I run several containers using docker-compose. I was curious installing Portainer to see if there's any value to this tool.

I'm using docker-compose again to install Portainer.

(1). Setup Portainer

```
mkdir ~/code/docker/portainer
cd ~/code/docker/portainer
vi docker-compose.yml
```

(2). Paste content into docker-compose.yml file.

```
version: "3"
services:
  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer
    ports:
      - 9000:9000
    volumes:
      - portainer_data:/data
      - /var/run/docker.sock:/var/run/docker.sock
    restart: unless-stopped
volumes:
  portainer_data:
```

(3). Run Portainer.

```
docker-compose up -d
```

(4). Open your browser and open the [web interface](http://localhost:9000) on port 9000. 
