---
title: 'generate random characters'
author: ulysses

date: 2012-11-28
slug: generate-random-characters
draft: false
---

This article will show you how to generate random characters in PHP. Random characters are useful in a variety of ways, such as generating random passwords or filenames. The command that we are going to use to generate random characters is a function called mt\_rand(). In addition, we will specify which characters we want to include in our random key.

I’ve decided to omit vowels, as well as the number zero, to make the random characters much more unpredictable. I’ve added some special characters in the mix, just for the fun of it. If you don’t want the special characters, you can just take them out. Here’s our list.

```
// List of random characters
$characters = array(
	"B","C","D","F","G","H","J","K","L",
        "M","N","P","Q","R","S","T","V","W",
        "X","Y","Z","b","c","d","f","g","h",
        "j","k","l","m","n","p","q","r","s",
        "t","v","w","x","y","z",
        "1","2","3","4","5","6","7","8","9",
	"!","@","#","$","%","^","*","(",")",
	"+","=","{","}","[","]","~"
);
```

Next, we will create a variable array to store our random key. We will run a loop 7 times, to generate a key that is 7 characters long. Inside the loop, we count the number of characters on our list, and generate a key, one by one, until the loop is done. Finally, we reveal our random key on the screen using the echo command. Just reload the page to generate a different key.

```
// Assign an array for our random key
$keys = array();
// generate random key 7 times
while(count($keys)
```

<a href="http://uly.me/demo/random.php" target="_blank">Demo</a>