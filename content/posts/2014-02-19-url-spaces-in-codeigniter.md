---
title: 'url spaces in codeigniter'
author: ulysses

date: 2014-02-19
slug: url-spaces-in-codeigniter
draft: false
---

I ran into some issues with a piece of code I wrote several years ago in CodeIgniter. I’m using names of people as part of the URL. When someone enters a name with spaces on the database, the spaces are converted to %20 in the resulting URL. The URL doesn’t look pretty and definitely not SEO friendly. It needs to be cleaned up by replacing spaces with either a dash or an underscore.

The other issue is when performing a search, the database doesn’t really know that ‘John Doe’ is essentially the same as ‘John%20Doe.’ So, I ended up using a CodeIgniter function called url\_title. The function strips the spaces and replaces it with a dash or a hyphen. In the case of ‘John%20Doe’, it now displays as ‘John-Doe.’ You can also use an underscore. See example below.

Replace %20 with dash or hypen

```
$name = 'John Doe';
$url = url_title($name);
// produces 'John-Doe'

$name = 'John Doe';
$url = url_title($name, '_');
// produces 'John_Doe'
```

Put the space before the search

Before performing a search, I use str\_replace to remove the dash and put back the space so it matches the database entry. It’s essentially the reverse of what I did to display a friendly URL.

```
$url = 'John-Doe';
$name = str_replace('-', ' ', $url);
// perform your search function here
```

If you’re not familiar with CodeIgniter, check how [URI routing](http://ellislab.com/codeigniter%20/user-guide/general/routing.html) and [url\_title](http://ellislab.com/codeigniter%20/user-guide/helpers/url_helper.html) are handled.