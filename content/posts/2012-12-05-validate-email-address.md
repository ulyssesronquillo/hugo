---
title: 'validate email address'
author: ulysses

date: 2012-12-05
slug: validate-email-address
draft: false
---

I was working with PHP forms the other day which contained an email address. Validating email addresses is important. Occasionally, email addresses are used for activating accounts or resetting passwords. We can’t always guarantee that the email address provided is going to be valid, but at least, we can validate it’s going to be in the correct format. For pattern matching, I’m using a regex I found online. I like it because it’s very strict. I’m using the regex pattern with the preg\_match function to determine a valid email address.

```
function check_email($email) {
 $pattern = "/^([a-zA-Z0-9])+([a-zA-Z0-9\._+-])*@([a-zA-Z0-9_-])+([a-zA-Z0-9\._-]+)+$/";
 if (!preg_match($pattern, stripslashes(trim($email)))) :
  return false;
 else :
  return true;
 endif;
}
```

To use the function, we can do this.

```
$email = "name@domain.com";
echo $message = (check_email($email) ? "Valid." : "Wrong format.");
```

In this example above, I’m using a ternary operator to display the result. It echoes out “Valid” because the email address we provided is in a valid format. You can use the regular “if else” conditional, if you prefer, instead of the ternary operator. By the way, I set $email variable manually. It this was an actual application, the email address cloud have come from a form.