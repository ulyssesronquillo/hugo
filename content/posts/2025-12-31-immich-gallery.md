---
author: ulysses
title: 'immich gallery'
date: 2025-12-31
slug: immich-gallery
draft: false
---
If you like hosting a photo gallery on your own desktop or server, give Immich a try.

I installed mine on my Linux Mint desktop using docker compose.

(1). Create a directory.

```
mkdir immich; cd immich
```

(2). Download a couple of files.

```
wget -O docker-compose.yml https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml
wget -O .env https://github.com/immich-app/immich/releases/latest/download/example.env
```

(3). Customize the .env file with your custom values.

```
UPLOAD_LOCATION=
DB_DATA_LOCATION=
DB_PASSWORD=
```

(4). Start the container.

```
docker compose up -d
```

(5). Finally, access the gallery from your browser.

```
http://localhost:2283
# or via ip address
http://xxx.xxx.xxx.xxx:2283
```

