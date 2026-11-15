---
title: 'gcp web server'
author: ulysses

date: 2020-01-08
slug: gcp-web-server
draft: false
---

Here’s a quick script to stand up a web server based on Centos image.

```
gcloud compute instances create [VM-NAME] \
    --zone=[ZONE] \
    --image-family=debian-9 \
    --image-project=debian-cloud \
    --tags=allow-ssh,allow-health-check \
    --subnet=lb-subnet \
    --metadata=startup-script='#! /bin/bash
apt-get update
apt-get install apache2 -y
a2ensite default-ssl
a2enmod ssl
vm_hostname="$(curl -H "Metadata-Flavor:Google" \
http://169.254.169.254/computeMetadata/v1/instance/name)"
echo "Page served from: $vm_hostname" | \
tee /var/www/html/index.html
systemctl restart apache2'
```