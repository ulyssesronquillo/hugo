---
title: 'list available php modules'
author: ulysses

date: 2020-03-02
slug: list-available-php-modules
draft: false
---

Here’s how to list the available PHP modules.

```
apt-cache search php- | less
```

To get details about a module.

```
apt-cache show php-curl
```

To install a module.

```
apt install php-curl
```

Or install all modules.

```
apt install php*
```

Restart Apache after each install.

```
systemctl restart apache2
```