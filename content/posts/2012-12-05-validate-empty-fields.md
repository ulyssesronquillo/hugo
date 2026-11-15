---
title: 'validate empty fields'
author: ulysses

date: 2012-12-05
slug: validate-empty-fields
draft: false
---

Here’s a simple way to validate forms with empty fields. When working with forms, we want users to submit required fields. We can easily check by using the PHP empty() function. In this example, I will use a simple form, and check if “username” is empty. Since the action for the form is blank, the form will submit to itself. The the code you see for “value” is a shorthand PHP code to echo the field entry after a submit.

```
<form action="" method="post" name=""> 
<input name="username" type="text" value="<?=$username;?"></input>
<input name="submit" type="submit" value="Submit"></input>
</form>
```

Here’s the PHP code. First, we need to check if the form was submitted. We do this by checking $\_POST\[‘submit’\]. Next, we will check if “username” is empty by using the empty() PHP function. If it’s empty, then we assign an error message to $errors. Finally, we will check if $errors is empty. If it is, then we can proceed with whatever we want to do. Otherwise, we echo the error messages.

```
$errors = array();
if (isset($_POST['submit'])) :
 $username = $_POST['username'];
 if (empty($username)) $errors[] = "Empty username.";
 if (empty($errors)) : 
  // do something special here, like saving to a database.
 else:
  // otherwise print the error messages.
  foreach ($errors as $msg) :
   echo "$msg<br></br>\n";
  endforeach;
 endif;
endif;
```

And one more thing. Place this PHP code above your form. The reason for this is, we want to redisplay the form just below the error messages. Users will be able to see the error messages right away, and the form is right there in front of the user ready for editing again.