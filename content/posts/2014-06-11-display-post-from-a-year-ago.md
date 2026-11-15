---
title: 'display post from a year ago'
author: ulysses

date: 2014-06-11
slug: display-post-from-a-year-ago
draft: false
---

Here’s a cool little WordPress script to display a post from a year ago. You can display your old content to entice your readers to view older articles. You can display your old posts on your theme’s sidebar, after your post content, or just anywhere on your theme. Here’s the code.

```
// current day of the month without leading zeros, e.g. 1-31.
$current_day = date('j');
// last year
$last_year = date('Y')-1;
// perform a query based on today's date last year
query_posts('day='.$current_day.'&year='.$last_year);
if (have_posts()):
    while (have_posts()) : the_post();
       the_title();
       the_excerpt();
    endwhile;
endif;
```

The result will depend if you have a post last year on the exact date as today, otherwise you’ll get a blank result. I suppose to be on the safe side, you can query all posts of the current month last year. Your chances of getting results is much better. You can use the date(‘n’) function to extract the current month. Your query would look something like this:

```
$current_month = date('n');
query_posts('month='.$current_month.'&year='.$last_year);
```