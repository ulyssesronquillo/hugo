---
title: 'run sql in bash'
author: ulysses

date: 2019-03-10
slug: run-sql-in-bash
draft: false
---

Here’s an example on how to run MySQL commands from Bash.

```
mysql dbname -e "UPDATE wp_options SET option_value='http://domain.com' WHERE option_name='home'";
mysql dbname -e "UPDATE wp_options SET option_value='http://domain.com' WHERE option_name='siteurl'";
```

The example updates WordPress’ home and siteurl. Script contains no password. It’s using .my.cnf config file.