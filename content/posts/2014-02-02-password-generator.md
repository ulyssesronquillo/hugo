---
title: 'password generator'
author: ulysses

date: 2014-02-02
slug: password-generator
draft: false
---

Yahoo got hacked again. Based on what I read, not everyone was affected. Yahoo has over 273 million users using their mail service. If you haven’t received an email from Yahoo asking you to reset your password, you are probably ok. But, you could never be so sure. Better reset your password.

Like most users, we probably use the same password across many sites. It’s doesn’t sound like a good idea now. If one website gets hacked, all your other accounts are possibly compromised as well. As a good security practice, it’s probably a good idea to use different passwords for different accounts.

Coming up with a difficult password is not always easy. There are numerous sites that auto-generate passwords for you. You can specify the level of difficulty. You can make it 6, 7, or 8 characters. You can include numbers, special characters and use capitalization.

Instead of going to websites and auto-generating passwords for you, you could do it yourself. You can learn how to randomly create passwords. In this article, I will share with you how you can auto-generate passwords using the PHP language, and in particular using PHP function called mt\_rand().

First, let’s specify what characters we want to include in our password. We will use both uppercase and lowercase. No vowels. Numbers 1 to 9. Finally, we will include some specials characters to spice things up. We will assign all the characters that we want included to a variable called $characters.

The Characters

```
// list of random characters
$characters = array(
  "B","C","D","F","G","H","J","K","L","M","N","P","Q","R","S","T","V","W","X","Y","Z",
  "b","c","d","f","g","h","j","k","l","m","n","p","q","r","s","t","v","w","x","y","z",
  "1","2","3","4","5","6","7","8","9",
  "!","@","#","$","%","^","*","(",")","+","=","{","}","[","]","~"
);
```

In this example, we will use a 7 character password. We will create a loop that will be executed 7 times. It will randomly pick a character from the $characters array. It will check to see if the character was already picked. It will pick another if it is. It will then store the characters in an array called $keys until all 7 characters are picked.

The while loop checks how many characters are in the array and will stop until all 7 characters are picked. The mt\_rand() function randomly picks the characters. The in\_array() function checks to see if the character was already picked in the array.

The Random Keys

```
// Assign an array for our random key
$keys = array(); 
// generate random key 7 times
while(count($keys)
```

Now that we have our 7 character key, let's display it on the screen. Since it's in an array, we will extract it one by one using the while loop and assign the keys to a variable called $random_chars. Finally, we will echo the variable $random_chars to display our auto-generated password to the screen.

<h4>Display the Keys</h4>

```
foreach($keys as $key) :
	$random_chars .= $characters[$key];
endforeach;
// display random key
echo $random_chars;
```

If you like to see how it works, check out the <a href="http://uly.me/demo/random.php">demo</a>. Click refresh to view a different result.