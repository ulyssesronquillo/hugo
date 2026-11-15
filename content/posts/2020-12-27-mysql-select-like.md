---
title: 'mysql select like'
author: ulysses

date: 2020-12-27
slug: mysql-select-like
draft: false
---

Here’s how to perform SQL searches using the like operator.

```
# Format
SELECT column1, column2 FROM table_name WHERE column LIKE pattern;
# Search for an entry starting with a 'joe.'
SELECT id,username,address FROM users WHERE username LIKE 'joe%';
# Search for an entry ending with a 'joe.' 
SELECT id,username,address FROM users WHERE username LIKE '%joe';
# Search for any entry with 'joe' from any position. 
SELECT id,username,address FROM users WHERE username LIKE '%joe%';
# Finally, using "_" as wildcards. Find any field with "j" in the second position.
SELECT id,username,address FROM users WHERE username LIKE '_j';
```