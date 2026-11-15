---
title: 'modifying the content of your blog'
author: ulysses

date: 2014-03-14
slug: modifying-the-content-of-your-blog
draft: false
---

I wrote a custom blog in CodeIgniter two years ago. I revisited the code to change the content format a bit. I’ve noticed that there were several pieces of code that were commented out. At the time, I was playing around with what I could potentially do with the content. I thought I would share it here, because it will show you how you could drastically change the content of a blog by manipulating the content.

Let’s say the content of your blog is assigned to a variable called $item-&gt;content. We can alter the content by passing PHP functions to it. Let’s say we want to limit the content to just the first 330 characters. We can use a PHP function called substr. Substr returns a portion of the string from a specified start and length.

The Excerpt

```
$item->content = substr($item->content,0,330);
echo $item->content;
```

In this example, we are limiting content to the first 330 characters.

Remove page breaks and new lines

```
$item->content = str_replace(array('\r', '\n'), '', $item->content);
echo $item->content;
```

In this example, str\_replace replace page breaks and new lines with ” or nothing.

Remove two spaces

```
$item->content = str_replace('  ', '', $item->content);
echo $item->content;
```

Finally, adding Read More \[…\]

```
$item->content = $item->content . '<a href="#">Read [...]</a>';
echo $item->content;
```

I appended to content a link with the anchor of ‘Read \[…\].’