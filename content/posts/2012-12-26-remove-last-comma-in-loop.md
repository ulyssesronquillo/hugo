---
title: 'remove last comma in loop'
author: ulysses

date: 2012-12-26
slug: remove-last-comma-in-loop
draft: false
---

When performing a database query, we normally use a loop to output the database result. This is a common exercise for programmers when displaying results to the screen. To make the output readable, commas are typically used to separate data. Consider a loop below that prints a list of names. We added a string **‘, ‘** after each name to make it readable.

```
foreach($query as $item) :
echo $item->name.', '; 
endforeach;
```

The output would be something like this:  
John, Mary, Steve, Mark,

The output works as intended, but there is a trailing comma at the end that we don’t want. We either need to get rid of it, or replace it with a period. So, how do we do that? Here’s how.

We will use the trim() function to remove the last comma. But before we can do that, we should probably hold off on echoing to the screen until the loop is finished. So, we will store the results in a variable called $result as we go through the loop. To avoid a PHP undefined variable error, we need to initialize the $result variable before the loop begins. After the loop, we will use the rtrim function to remove the last comma. Finally, we echo the trimmed results and add a period.

```
$result="";
foreach($query as $item) :
$result.=$item->name.', '; 
endforeach;
$trimmed=rtrim($result, ', ');
echo $trimmed;
echo '.';
```

The output is now:  
John, Mary, Steve, Mark.