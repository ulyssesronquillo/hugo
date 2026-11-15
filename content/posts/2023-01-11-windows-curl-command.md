---
title: 'windows curl command'
author: ulysses

date: 2023-01-11
slug: windows-curl-command
draft: false
---

If you have to download a file from the Internet on a Windows server, can certainly use the browser. But if the browser is rendering the file instead of downloading them, you may have to use the curl command which is already pre-installed on most Windows servers. Just open the command line. Here’s the the curl command to download a file.

```
curl.exe --output index.txt --url https://website.domain/index.txt
```