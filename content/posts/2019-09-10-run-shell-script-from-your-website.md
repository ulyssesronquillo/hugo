---
title: 'run shell script from your website'
author: ulysses

date: 2019-09-10
slug: run-shell-script-from-your-website
draft: false
---

Here’s how to run a shell script from your website. You’ll need 2 files.

Here’s the contents of foo.php. Wrap your output with ‘pre’ for better formatting.

```
<?php $output = shell_exec('/var/www/html/bar.sh 2?>&1');
echo "$output";
```

Here’s the content of bar.sh. Output will be displayed on web page.

```
#!/bin/bash
now="$(date +'%y%m%d')"
echo $now
aws s3 ls
```