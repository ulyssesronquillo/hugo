---
author: ulysses
title: 'truncate titles in jekyll'
date: 2024-01-01
slug: truncate-titles-in-jekyll
draft: false
---

I switched to a slightly different format in the home page to display the date first followed by the post titles. In addition to the format change, I wanted to truncate the titles that are longer than 40 characters to display only the first 40 characters followed by 3 dots or "..." at the end. The key to making this possible was to use Jekyll's advanced [filters](https://gist.github.com/JJediny/a466eed62cee30ad45e2), and in particular, using the truncate filter. Swapping the order of date and post titles was the easy part, but the key was using the truncate filter.

Here's the code.

```
post.title | downcase | truncate: 40, ' ...'
```

The downcase filter converts post.title to lowercase. 

The truncate filter truncates post.title longer than 40 characters and adds 3 dots at the end. 

Truncate requires 2 parameters: the length of the string and the characters to append to the string.