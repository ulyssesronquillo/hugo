---
title: 'failover test'
author: ulysses

date: 2018-06-24
slug: failover-test
draft: false
---

How to failover a website without actually doing a failover? It’s actually easier than you think. The key is to trick your computer that it’s pointing to a failover website. You can easily do this by editing your hosts file and adding a DNS entry. In both Linux and MacOS, you can edit the /etc/hosts file and add the failover site like the following below.

```
# /etc/hosts
# failover site
# xxx.xxx.xxx.xxx   yourdomain.com
```

xxx.xxx.xxx.xxx is the IP address of your failover site.  
If you need to test the failover site, just uncomment the IP address.  
Replace a comment if you’re done testing.