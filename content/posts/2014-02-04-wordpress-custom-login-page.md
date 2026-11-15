---
title: 'wordpress custom login page'
author: ulysses

date: 2014-02-04
slug: wordpress-custom-login-page
draft: false
---

We’ve all seen the default WordPress login page. It’s dull, bland, and boring. Typically, the login page is not part of the WordPress theme setup. Most theme designers don’t bother to change the login screen because it’s not really necessary. The cool thing is, it’s entirely feasible to customize the login page. This article will show you how to change your WordPress login page to something like below.

![wp-login](http://uly.me/wp-content/uploads/2014/02/wp-login.png)

Changing the WordPress Logo

We can replace the WordPress logo located on top of the login form by calling a WordPress hook called ‘login\_enqueue\_scripts.’ This hook is responsible for enqueuing items to the login page. In this example, we are assigning an image to ‘body.login div#login h1 a.’

Place the following code in your theme’s ‘functions.php’ file.

```
function urr_login_logo() { 
}
```

The ‘logo.png’ file is located in your theme’s ‘images’ folder. Why can’t I see the logo image? Believe me, it’s there. You can’t see it because I made it transparent. It would be visible if it were non-transparent. So, it’s possible to replace the WordPress logo or display nothing at all, like I just did just now, using a transparent image.

By the way, the image needs to be 80×80 pixels in size.

Adding a Background Image

How do we add a background image to the login page? Well, one thing worth noting, WordPress does not load your theme’s stylesheet when the login page is loaded. To style to the login page, we need to add our own custom stylesheet. It will be loaded when the login page is displayed.

Now, place the following code in your theme’s ‘functions.php’ file.

```
function urr_custom_login_css() {
echo '';
}
add_action('login_head', 'urr_custom_login_css');
```

This code above loads a stylesheet when the login page is loaded. It’s using the ‘login\_head’ hook.

Our Stylesheet

Create a file called login-style.css and place it inside our theme’s directory under the ‘css’ folder. We can now style our login page. The code below will apply a background image ‘darkwood.jpg’ to the login page. The form and its inputs are darkened, except for the submit button which remains unchanged. In addition, we also rounded the corners of the form.

```
body.login {
  background: #000 url('http://uly.me/wp-content/themes/minimum/images/darkwood.jpg') no-repeat fixed center;
}
div#login form { 
  background-color:#111;
  border-radius: 10px;
}
div#login form input#user_pass, div#login form input#user_login, div#login form input#rememberme {
  color: #aaa;
  background-color:#333;
  border: 1px solid #000;
  border-radius: 3px;
}
div#login form input#user_pass, div#login form input#user_login, div#login form input#rememberme {
  color: #aaa;
  background-color:#333;
}
```

Finally, upload your functions.php, login-styles.css and images files to your server. Enjoy your custom login page.