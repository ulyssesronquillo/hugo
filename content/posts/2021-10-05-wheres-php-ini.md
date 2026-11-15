---
title: 'where is php.ini?'
author: ulysses

date: 2021-10-05
slug: wheres-php-ini
draft: false
---

How to find where php.ini is being from the command line.

```
$ php -i | grep 'grep 'Configuration File'
Configuration File (php.ini) Path => /etc
Loaded Configuration File => /etc/php.ini
```
