---
title: 'python web server'
author: ulysses

date: 2022-05-20
slug: python-web-server
draft: false
---

Here’s a quick way to start a web server using Python (not recommended for production).

If you want to use python3, you may have to use explicitly use python3.

Check what versions you have first.

```
python --version
python3 --version
```

Start web server using port 8080 in the current directory.

```
python -m http.server 8080
```

If you want an alternate directory, use this -d option.

```
python -m http.server 8080 -d /tmp
```

It’s a great tool for quick downloads.