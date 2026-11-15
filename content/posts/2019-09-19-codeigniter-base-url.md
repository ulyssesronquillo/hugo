---
title: 'codeigniter base url'
author: ulysses

date: 2019-09-19
slug: codeigniter-base-url
draft: false
---

I have a CodeIgniter dev site in Google Cloud. The instance obtains a new IP address at every start. You can set the base URL to a domain or IP address in the “/application/config/config.php” file. Since it’s only a dev box, I don’t have a domain assigned. It’s accessible via IP address only which changes every time the instance is started. So here’s the workaround. I added some extra code in the config file to obtain the external IP address.

```
$realIP = file_get_contents("http://ipecho.net/plain");
$config['base_url'] = 'http://'.$realIP;
```

The code is using a service from ipecho.net which returns your external IP address. Works like a charm!