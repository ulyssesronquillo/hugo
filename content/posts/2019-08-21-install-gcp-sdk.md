---
title: 'install gcp sdk'
author: ulysses

date: 2019-08-21
slug: install-gcp-sdk
draft: false
---

Here’s how to install Google Cloud Platform SDK on the following.

Centos, Fedora and Redhat

```
# Setup Repo
sudo tee -a /etc/yum.repos.d/google-cloud-sdk.repo 
```

For Debian, Ubuntu, Mint.


```
# Create an environment variable for the correct distribution
export CLOUD_SDK_REPO="cloud-sdk-$(lsb_release -c -s)"
# Add the Cloud SDK distribution URI as a package source
echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
# Import the Google Cloud Platform public key
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
# Update the package list and install the Cloud SDK
sudo apt-get update && sudo apt-get install google-cloud-sdk
```