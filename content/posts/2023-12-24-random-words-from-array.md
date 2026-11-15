---
author: ulysses
title: 'Random words from array'
date: 2023-12-24
slug: random-words-from-array
draft: false
---

Here's how to to generate random words from an array in Bash using shuf.

```
FOOD=('Milk' 'Bread' 'Eggs' 'Sausage' 'Grits' 'Banana' 'Oatmeal')
shuf -e ${FOOD[@]}
Milk
Grits
Sausage
Oatmeal
Bread
Banana
Eggs
```

You can limit output to 3 by piping output using head -n 3.

```
FOOD=('Milk' 'Bread' 'Eggs' 'Sausage' 'Grits' 'Banana' 'Oatmeal')
shuf -e ${FOOD[@]} | head -n 3
Bread
Sausage
Eggs
```
