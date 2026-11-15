---
title: 'search second column for characters'
author: ulysses

date: 2023-10-24
slug: search-second-column-for-characters
draft: false
---

How to search the second column for string starting with.

Here are the contents of results.txt.

```
John 10
Mario 12
Derek 15
Mark 20
Matt 25
```

Display only individuals that are older than 20 using awk.

```
awk '$2 ~ /^20/' results.txt
```

Result.

```
Mark 20
Matt 25
```

You can easily adjust this to other columns.