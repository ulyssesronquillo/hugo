---
title: 'windows route add'
author: ulysses

date: 2020-01-14
slug: windows-route-add
draft: false
---

Here’s how to add a route in Windows. Open CMD as Administrator.

```
route add 10.10.10.10 mask 255.255.255.0 10.10.10.254
```

To make it persistent, add -p.

```
route add 10.10.10.10 mask 255.255.255.0 10.10.10.254
```

To display. Specifies IP 4 only.

```
route print -4
```