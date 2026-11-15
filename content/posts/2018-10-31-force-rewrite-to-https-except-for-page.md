---
title: 'force rewrite to https except for page'
author: ulysses

date: 2018-10-31
slug: force-rewrite-to-https-except-for-page
draft: false
---

Here’s how to force a rewrite pages to https except for a couple of pages.

```
RewriteEngine On

RewriteCond %{HTTPS} =off
RewriteCond %{REQUEST_URI} !^\/page1\/
RewriteCond %{REQUEST_URI} !^\/page2\/
RewriteRule (.*) https://%{HTTP_HOST}/$1 [L,R=301]    

RewriteCond %{HTTPS} =on
RewriteCond %{REQUEST_URI} \/page1\/ [OR]
RewriteCond %{REQUEST_URI} \/page2\/
RewriteRule (.*) http://%{HTTP_HOST}/$1 [L,R=301]
```

The first rule-set will redirect all pages not /page1/ or /page2/ to the same URL but https://.  
The second rule will make sure that /page1/ and /page2/ are redirected back to http:// if accessed via https://.

Here’s the [Stackdriver source](https://stackoverflow.com/questions/5818146/how-to-force-rewrite-to-https-except-for-a-few-pages-in-apache).