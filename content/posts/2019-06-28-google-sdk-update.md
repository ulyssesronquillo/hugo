---
title: 'google sdk update'
author: ulysses

date: 2019-06-28
slug: google-sdk-update
draft: false
---

How to upgrade Google SDK on Redhat, Fedora and Centos Linux.

```
gcloud components update
```

If you are having trouble running that command because the GCloud component manager is disabled, you can try the following commands which will achieve the same result as above.

```
sudo yum makecache && sudo yum update \
kubectl \
google-cloud-sdk \
google-cloud-sdk-app-engine-grpc \
google-cloud-sdk-pubsub-emulator \
google-cloud-sdk-app-engine-go \
google-cloud-sdk-cloud-build-local \
google-cloud-sdk-datastore-emulator \
google-cloud-sdk-app-engine-python \
google-cloud-sdk-cbt \
google-cloud-sdk-bigtable-emulator \
google-cloud-sdk-datalab \
google-cloud-sdk-app-engine-java
```