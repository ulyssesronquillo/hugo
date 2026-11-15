---
title: 'multiple virtualhosts'
author: ulysses

date: 2018-03-10
slug: multiple-virtualhosts
draft: false
---

Here’s the proper way to host multiple websites (domains) on single host with a single IP address. Technically, you can have multiple Apache configuration files that you can enable within Apache, but you can easily simplify and combine them into a single Apache configuration file. You can separate each domain by creating multiple virtualhost sections as shown in the example below.

```
<virtualhost>
    DocumentRoot "/www/example1"
    ServerName www.example.com
    # Other directives here
</virtualhost>

<virtualhost>
    DocumentRoot "/www/example2"
    ServerName www.example.org
    # Other directives here
</virtualhost>
```

If you’re interested, read up on Apache’s website about [virtual hosts](https://httpd.apache.org/docs/2.4/vhosts/examples.html).