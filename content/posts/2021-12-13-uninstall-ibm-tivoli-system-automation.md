---
title: 'uninstall ibm tivoli system automation'
author: ulysses

date: 2021-12-13
slug: uninstall-ibm-tivoli-system-automation
draft: false
---

How to uninstall IBM Tivoli System Automation from Linux.

Check if domain is online.

```
lsrpdomain
```

Stop the domain.

```
stoprpdomain <domain>
</domain>
```

Uninstall.

```
cd /opt/IBM/tsamp/sam/uninst/
./uninstallSAM
```

Check the logs.

```
/tmp/uninstallSAM..log
```