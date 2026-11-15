---
title: 'truncating page titles'
author: ulysses

date: 2014-01-29
slug: truncating-page-titles
draft: false
---

The title of an article is one of the most important factors for SEO. It’s second only to the content itself. The title has to be catchy, concise and relevant to the content. If you look at Google search results, they show roughly 70 characters of the title on the results page. If the title is too long, you’ll see 3 dots or ellipses as they’re appropriately called. There’s really no ideal length for titles, as long as they best describe the content of the page. They can be short or long and must contain certain keywords.

If the title is too long, it can sometimes wreak havoc to the layout of the theme. There are times that you may have to trim the title so it doesn’t become such an eyesore. If you need to truncate the title, there is a function in PHP called ‘substr’ which returns parts of a string. In WordPress, page titles can be retrieved using a function called the\_title(). We can truncate this string, by creating a new function called truncate().

```
<?php // lets create truncate function
function truncate($the_title) {
  $the_new_title = substr($the_title, 0, 70);
  if (strlen($the_title) ?> 70) $the_new_title .= ' ...';
  return $the_new_title;
}

// assign the title to a variable
$the_title = the_title();

// we call the truncate function
echo truncate($the_title); 
```

In this example above, we created a new function called truncate(). We passed a variable containing the title to the function. Substr will trim the title string starting at location 0, and will preserve it for the next 70 characters. The strlen function counts the string, and adds ellipses at the end if the string is longer than 70 characters. The truncated value is then returned. It can be echoed for display if we want. We can place this new function anywhere in our theme files. We can insert it in the main WordPress loop or on single pages.