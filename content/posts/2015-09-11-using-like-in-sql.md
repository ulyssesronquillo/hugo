---
title: 'using like in sql'
author: ulysses

date: 2015-09-11
slug: using-like-in-sql
draft: false
---

I was looking at my SQL statements the other day. I was doing a bunch of comparisons with a certain field that contain a pattern of words. My original SQL was quite tedious as displayed below. After much thought, I was able to pare it down to something much simpler. The newer SQL statement is much shorter and to the point. It uses the operator LIKE to search for a pattern.

OLD SQL

```
SELECT 
  * 
FROM 
  mytable 
WHERE 
( product="model-1" or
  product="model-2" or 
  product="model-3" or
  product="model-4" or
  product="model-5" or
  product="model-6" ) AND
  id=105
```

NEW SQL

```
SELECT 
  * 
FROM 
  mytable 
WHERE 
  product LIKE "%model%" AND
  id=105
```

The newer SQL is a vast improvement over the previous one. I was also forced to use parenthesis around the previous SQL statement to group together the OR comparisons. Without the parenthesis, my results were inaccurate because the AND had precedence over the OR. With an improved SQL, there’s no need to use parenthesis. Obviously the LIKE operator only works if there’s a pattern. I use % to make the search more liberal, otherwise it would look for an exact match.