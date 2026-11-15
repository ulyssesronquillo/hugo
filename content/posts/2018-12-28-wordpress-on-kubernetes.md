---
title: 'wordpress on kubernetes'
author: ulysses

date: 2018-12-28
slug: wordpress-on-kubernetes
draft: false
---

[Kubernetes](http://kubernetes.io) has documentation on how to deploy [WordPress](http://wordpress.org) on its platform. The setup is using Persistent Volumes for both WordPress and MySQL on [MiniKube](https://github.com/kubernetes/minikube). Although the setup is not recommended for a production environment, it is a good start to get yourself familiar with Kubernetes. For production environments, they do recommend running WordPress on a Kubernetes cluster using the [Helm](https://github.com/helm/charts/tree/master/stable/wordpress) package manager. Here’s the WordPress-MySQL [deployment on MiniKube.](https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/)

```
apiVersion: v1
kind: Service
metadata:
  name: wordpress-mysql
  labels:
    app: wordpress
spec:
  ports:
    - port: 3306
  selector:
    app: wordpress
    tier: mysql
  clusterIP: None
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: mysql-pv-claim
  labels:
    app: wordpress
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 20Gi
---
apiVersion: apps/v1 # for versions before 1.9.0 use apps/v1beta2
kind: Deployment
metadata:
  name: wordpress-mysql
  labels:
    app: wordpress
spec:
  selector:
    matchLabels:
      app: wordpress
      tier: mysql
  strategy:
    type: Recreate
  template:
    metadata:
      labels:
        app: wordpress
        tier: mysql
    spec:
      containers:
      - image: mysql:5.6
        name: mysql
        env:
        - name: MYSQL_ROOT_PASSWORD
          valueFrom:
            secretKeyRef:
              name: mysql-pass
              key: password
        ports:
        - containerPort: 3306
          name: mysql
        volumeMounts:
        - name: mysql-persistent-storage
          mountPath: /var/lib/mysql
      volumes:
      - name: mysql-persistent-storage
        persistentVolumeClaim:
          claimName: mysql-pv-claim
```