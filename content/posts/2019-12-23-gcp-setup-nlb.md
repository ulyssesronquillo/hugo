---
title: 'gcp setup nlb'
author: ulysses

date: 2019-12-23
slug: gcp-setup-nlb
draft: false
---

Here’s how to setup a Network Load Balancer in GCP.

Setup your instances.

```
# Instance 1
gcloud compute instances create www1 \
  --image-family debian-9 \
  --image-project debian-cloud \
  --zone us-central1-b \
  --tags network-lb-tag \
  --metadata startup-script="#! /bin/bash
    sudo apt-get update
    sudo apt-get install apache2 -y
    sudo service apache2 restart
    echo '<h1>www1</h1>' | tee /var/www/html/index.html
    EOF"
# Instance 2
gcloud compute instances create www2 \
  --image-family debian-9 \
  --image-project debian-cloud \
  --zone us-central1-b \
  --tags network-lb-tag \
  --metadata startup-script="#! /bin/bash
    sudo apt-get update
    sudo apt-get install apache2 -y
    sudo service apache2 restart
    echo '<h1>www2</h1>' | tee /var/www/html/index.html
    EOF"
# Instance 3
gcloud compute instances create www3 \
  --image-family debian-9 \
  --image-project debian-cloud \
  --zone us-central1-b \
  --tags network-lb-tag \
  --metadata startup-script="#! /bin/bash
    sudo apt-get update
    sudo apt-get install apache2 -y
    sudo service apache2 restart
    echo '<h1>www3</h1>' | tee /var/www/html/index.html
    EOF"
```

Create a firewall to allow external traffic to reach port 80.

```
gcloud compute firewall-rules create www-firewall-network-lb \
    --target-tags network-lb-tag --allow tcp:80
```

Configure your network load balancer.

```
# Create an external IP address.
gcloud compute addresses create network-lb-ip-1 \
    --region us-central1
# Add a legacy HTTP health check.
gcloud compute http-health-checks create basic-check
# Add a target pool.
gcloud compute target-pools add-instances www-pool \
    --instances www1,www2,www3 \
    --instances-zone us-central1-b
# Add a forwarding rule.
gcloud compute forwarding-rules create www-rule \
    --region us-central1 \
    --ports 80 \
    --address network-lb-ip-1 \
    --target-pool www-pool
# Lookup external IP address.
gcloud compute forwarding-rules describe www-rule \
    --region us-central1
```

Finally, use the curl command to send traffic to the NLB external IP address.

```
while true; do curl -m1 [IP_ADDRESS]; done
```