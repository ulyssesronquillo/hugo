---
title: 'add files in wordpress without ftp'
author: ulysses

date: 2016-03-22
slug: add-files-in-wordpress-without-ftp
draft: false
---

I’m working on a client site running WordPress but without any access to FTP. It’s an interesting dilemma because WordPress will allow you to add new themes and plugins via its interface. It does so by allowing you to upload zipped files of the themes and plugins. Obviously, you don’t want to keep doing this especially you want to add just one file to the theme.

I needed to create a new page template on the Genesis platform. My client is using the Enterprise Pro child theme. There’s a command in PHP called ‘touch’ which allows you to create a new file. You can insert this command on the top of your theme’s header file in WordPress. Since I’m using Genesis, the child theme doesn’t have a header, therefore I had to do insert the command in the parent theme.

In the WordPress Dashboard under Appearance, choose the Editor. On the top right-hand side of the page, select the Genesis parent theme from the dropdown menu to edit. Click on the ‘Theme Header’ to edit, and add this line of code on top of the header.php file.

```
touch('wp-content/themes/enterprise-pro/template.php');
```

The command has to run once, so you’ll need to access the website at least once. Remove the line of code afterwards. The PHP ‘touch’ function will create a new empty file called template.php inside the Enterprise Pro theme. You can check it by navigating the editor once again, and selecting this time the ‘Enterprise Pro’ theme. Look for the new file called ‘template.php.’

In my case, I decided to change the page template to another filename, so I ended running it for the second time by inserting the rename function on the header.php file once again. Here’s the command to rename template.php to newtemplate.php.

```
rename('wp-content/themes/enterprise-pro/template.php', 'wp-content/themes/enterprise-pro/newtemplate.php');
```

Anyway, it works, but use this with extreme caution. If you’re not familiar with PHP and WordPress, you can render the entire website useless if you somehow inserted the wrong PHP code. There’s no FTP to back out the files. The WordPress Dashboard may no longer work. So, work on your own peril.