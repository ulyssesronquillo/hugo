---
title: 'sorting arrays'
author: ulysses

date: 2012-11-27
slug: sorting-arrays
draft: false
---

I was working on a client project last night. I had to sort a multidimensional array. I came across a neat PHP function called asort. In the end, I had to use arsort instead of asort to get a reverse sort order. This short article will show you how to sort arrays in normal and reverse order. Here’s our array.

```
$animals = array("a" => "Giraffe", "b" => "Elephant", "c" => "Lion");
```

We will sort the array using the asort function. We print the array to view the results.

```
asort($animals);
print_r($animals);
```

The asort output is:

```
Array ( [b] => Elephant [a] => Giraffe [c] => Lion )
```

The arsort (reverse order) output is:

```
Array ( [c] => Lion [a] => Giraffe [b] => Elephant )
```