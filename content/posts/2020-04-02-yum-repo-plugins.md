---
title: 'yum repo plugins'
author: ulysses

date: 2020-04-02
slug: yum-repo-plugins
draft: false
---

Here’s how to disable plugin in Yum repos.

```
# check which plugins are enabled
yum repolist
# disable plugins
yum update --disableplugin=product-id,subscription-manager
# check agin
yum repolist
```

If that doesn’t work, check the individual config files of each plugin.

```
cd /etc/yum/pluginconf.d/
vim product-id.conf
vim subscription-manager.conf
```

Disable it.

```
[main]
enable=0
```