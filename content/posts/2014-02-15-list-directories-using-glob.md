---
title: 'list directories using glob'
author: ulysses

date: 2014-02-15
slug: list-directories-using-glob
draft: false
---

If there’s a need for you to list directories on the server, there’s a PHP function called [Glob](http://us2.php.net/glob) which will find pathnames to match a certain pattern. To make glob read only directories on the server, we can specify in the glob function with the GLOB\_ONLYDIR option which will return only directories and ignore files. The asterisk means it will accept any pattern.

```
glob('*', GLOB_ONLYDIR);
```

In the example below, we will specify any directory by assigning an empty or a blank to the $dir variable. We will then use the foreach loop to display all directories found. If we have WordPress installed, we can ignore the WordPress directories by searching for them in the if statement. We will finally echo and print to the screen each individual directory found by our glob function.

Here’s the entire script with HTML included.

```
<title>Glob - list directories</title>
<style>
  li { list-style-type:none; margin-left:-15px; }
</style>
<h1>List directories using Glob</h1>
```

```
<?php // set to current directory 
$dir = '';
// directories only. ignore files, etc.
foreach(glob($dir.'*', GLOB_ONLYDIR) as $folder){ 
  // do not include wordpress directories
  if (($folder != 'wp-admin') && ($folder != 'wp-content') && ($folder != 'wp-includes')) { 
    // list directories and their links
  ?> - ["&gt;<?php echo $folder;??>](<<?php echo $dir.>)
 <?php }
} 
?>
```