---
author: ulysses
title: 'install azure cli'
date: 2024-12-30
slug: install-azure-cli
draft: false
---

Install the Azure CLI on a Linux Desktop. This one of 2 options, but this is by far the easiest.

```
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

Validate Azure CLI is installed 

```
az --version
```

To upgrade

```
az upgrade
```

