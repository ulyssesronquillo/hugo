---
title: 'static website on gke'
author: ulysses

date: 2019-12-25
slug: static-website-on-gke
draft: false
---

Here’s how to run your web application on Google Kubernetes Engine.

Create a Dockerfile. Place your web pages in the public-html directory.

```
FROM httpd:2.4
COPY ./public-html/ /usr/local/apache2/htdocs/
```

Build a container image for Google Container Registry (GCR).

```
# set your project
export PROJECT_ID=[project_id]
# build a container image
docker build -t gcr.io/${PROJECT_ID}/your-app:v1 .
# verify docker images
docker images
```

Upload the container image to GCR.

```
# authenticate
gcloud auth configure-docker
# upload image
docker push gcr.io/${PROJECT_ID}/your-app:v1
```

Create a container GKE cluster.

```
# create cluster
gcloud container clusters create your-app-cluster \
--num-nodes=2
# check clusters
gcloud compute instances list
```

Deploy your web application.

```
# create deployment
kubectl create deployment your-app \
--image=gcr.io/${PROJECT_ID}/your-app:v1
# see the pods
kubectl get pods
```

Expose your application to the Internet.

```
# expose your application
kubectl expose deployment your-app \
--type=LoadBalancer \
--port 80 \
--target-port 80
# get the external ip address
kubectl get service
```

Scale your application.

```
# scale to 3 replicas
kubectl scale deployment your-app --replicas=3
# display the replicas
kubectl get deployment your-app
```

Cleanup.

```
kubectl delete service your-app
gcloud container clusters delete your-app-cluster
```