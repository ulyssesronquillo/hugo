---
author: ulysses
title: 'nginx rtmp streaming docker'
date: 2025-01-08
slug: nginx-rtmp-streaming-docker
draft: false
---

Create a nginx.conf file.

```
worker_processes  1;
events {
    worker_connections  1024;
}
rtmp {
    server {
        listen 1935;
        chunk_size 4096;
        application live {
            live on;
            record off;
            hls on;
            hls_path /hls;
        }
    }
}
http {
    server {
        listen 80;
        root /hls;
        location / {
            add_header 'Access-Control-Allow-Origin' '*';
            index index.html index.htm;
        }
        location /hls {
            types {
                application/vnd.apple.mpegurl m3u8;
                video/mp2t ts;
            }
            add_header 'Access-Control-Allow-Origin' '*';
            alias /hls;
        }
    }
}
```

Create a docker-compose.yml file.

```
version: "3.7"
services:
  nginx:
    image: tiangolo/nginx-rtmp
    restart: always
    ports:
      - "1935:1935" # RTMP port
      - "8090:80"   # HTTP port for HLS playback
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
```
Start the RTMP server.

```
docker-compose up -d
```
Stop the RTMP server.

```
docker-compose down
```
Livestream a MP4 video to your RTMP server using ffmpeg.

```
ffmpeg -re -i bunny.mp4 -c:v libx264 -c:a aac -f flv rtmp://localhost:1935/live/stream
```
Point your player to the RTMP service.

```
http://localhost:8090/hls/stream.m3u8
```
See my previos post.
