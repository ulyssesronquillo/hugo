---
title: 'awscli cli_pager'
author: ulysses

date: 2021-09-05
slug: awscli-cli_pager
draft: false
---

In AWSCLI Version 2, it’s using “less” by default to send output to the screen. Less displays output one page at a time.

If less interferes with your script, then you can set “cli\_pager” in ~/.aws/config to use nothing.

```
[default]
region = us-east-2
output = json
cli_pager =
```

If you have other profiles, add them as well.

```
[lightsail]
region = us-east-2
output = json
cli_pager =
```