---
author: ulysses
title: 'lower to upper vice versa'
date: 2024-09-11
slug: lower-to-upper-vice-versa
draft: false
---
How to convert uppercase to lowercase and vice versa.

```
upper_project=$(echo "$project" | tr '[:lower:]' '[:upper:]')
```

Vice versa

```
lower_project=$(echo "$project" | tr '[:upper:]' '[:lower:]')
```

Display output

```
echo $upper_project
echo $lower_project
```

