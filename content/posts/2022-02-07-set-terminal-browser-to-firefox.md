---
title: 'set terminal browser to firefox'
author: ulysses

date: 2022-02-07
slug: set-terminal-browser-to-firefox
draft: false
---

Every time I log in to Google Cloud, it’s using the Chromium.

Set BROWSER env to Firefox instead.

```
export BROWSER=/usr/bin/firefox
```

Login to GCP. It should open up Firefox browser instead of Chromium.

```
gcloud auth login
```

Add it your .bashrc or .bashprofile if you want it to be permanent.