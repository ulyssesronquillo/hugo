---
title: 'aws lightsail blueprints'
author: ulysses

date: 2021-01-01
slug: aws-lightsail-blueprints
draft: false
---

[Amazon Lightsail](https://aws.amazon.com/lightsail/) offers a variety of OS blueprints, starting from Amazon Linux 2, Ubuntu 20, Windows Server 2019 to Debian 10 to name just a few. Blueprints are a curated selection of operating systems and software that are preinstalled for the creation of instances. For brevity, only a subset of blueprints are displayed below. The description and licenseUrl portions are truncated. To display an entire list of LightSail blueprints, run this command.

```
aws lightsail get-blueprints --region us-east-1
```

Output:

```
{
  "blueprints": [
        {
            "blueprintId": "ubuntu_20_04",
            "name": "Ubuntu",
            "group": "ubuntu_20",
            "type": "os",
            "description": "Ubuntu 20.04 LTS - Focal. Lean, fast and powerful, Ubuntu Server delivers services reliably ...",
            "isActive": true,
            "minPower": 0,
            "version": "20.04 LTS",
            "versionCode": "1",
            "productUrl": "https://aws.amazon.com/marketplace/pp/B087QQNGF1",
            "licenseUrl": "https://d7umqicpi7263.cloudfront.net/eula/product/aced0818- ... .txt",
            "platform": "LINUX_UNIX"
        },
        {
            "blueprintId": "wordpress",
            "name": "WordPress",
            "group": "wordpress",
            "type": "app",
            "description": "Bitnami, the leaders in application packaging, and Automattic, the experts behind WordPress .... ",
            "isActive": true,
            "minPower": 0,
            "version": "5.6.0",
            "versionCode": "1",
            "productUrl": "https://aws.amazon.com/marketplace/pp/B00NN8Y43U",
            "licenseUrl": "https://d7umqicpi7263.cloudfront.net/eula/product/7d426cb7- ... .txt",
            "platform": "LINUX_UNIX"
        }
}
```

In this example, I’m using the query option to display only the blueprints ids.

```
aws lightsail get-blueprints --query 'blueprints[*].[blueprintId]' --output text --region us-east-1
```

Output:

```
windows_server_2019
windows_server_2016
windows_server_2012
windows_server_2016_sql_2016_express
amazon_linux_2
amazon_linux
ubuntu_20_04
ubuntu_18_04
ubuntu_16_04_2
debian_10
debian_9_5
debian_8_7
freebsd_12
opensuse_15_1
centos_7_1901_01
wordpress
wordpress_multisite
lamp_7
nodejs
joomla
magento
mean
drupal
gitlab
redmine
nginx
ghost_bitnami
django_bitnami
plesk_ubuntu_18_0_28
cpanel_whm_linux
```