---
title: 'get directory size'
author: ulysses

date: 2019-09-07
slug: get-directory-size
draft: false
---

Here’s how to get the size of a directory.

```
du -sh /var/www
```

Output:

```
2.1GB    /var/www
```

Size of the directories and files one level down.

```
du -sh /var/www/*
```

Sort with biggest files from top to bottom.

```
du -sh /var/www/* | sort -rh
```

Top 5 biggest files from top to bottom.

```
du -sh /var/www/* | sort -rh | head -5
```