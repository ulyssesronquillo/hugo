---
title: 'heredoc in php'
author: ulysses

date: 2014-03-02
slug: heredoc-in-php
draft: false
---

Heredoc is a way of displaying simplified code in many programming languages. Heredoc is available in PHP and other major languages such as Python, Ruby, and others. If you were to display a HTML form within PHP, you could go in and out of PHP, or use the echo or printf functions within PHP. Any quotes found inside the main quotes would need to be escaped with a backlash or \\. Another trick is to alternatively use single and double quotes. If the string is long, I imagine it can get confusing. Wouldn’t be nice if there was simpler way of doing it. So, here is heredoc coming to the rescue. The following code shows the different ways of presenting HTML within PHP.

Weaving in and out of PHP

```
<?php // some PHP code here ?>
<form> First name: <input name="firstname" type="text"></input>  
 Last name: <input name="lastname" type="text"></input>
</form>
<?php // some more PHP code?>
```

Staying within PHP and using the echo function. Quotes are escaped.

```
<?php // some PHP code here
echo "<form?>";
echo "First name: <input name="\"firstname\"" type="\"text\""></input><br></br>";
echo "Last name: <input name="\"lastname\"" type="\"text\""></input>";
echo "";
// some more PHP code
?>
```

Using single quotes and double quotes.

```
<?php // some PHP code here
echo '<form>'; 
echo 'First name: <input name="firstname" type="text"></input>'; 
echo 'Last name: <input name="lastname" type="text"></input>';
echo '</form>';
?>
<?php // some more PHP code ?>
```

Using heredoc

```
<?php // some PHP code here
echo = <<<HERE_DOC
<form?>
First name: <input name="firstname" type="text"></input><br></br>
Last name: <input name="lastname" type="text"></input>

HERE_DOC;
```

As you can see, Heredoc looks a lot cleaner especially if the form is quite lengthy. You can see the potential advantage as to why one should use Heredoc. To use Heredoc, there are certain rules worth mentioning. The ‘