---
title: 'where featured images are stored'
author: ulysses

date: 2017-03-10
slug: where-featured-images-are-stored
draft: false
---

The WordPress Genesis theme uses featured images on its posts on several of its themes. If you’re curious as to where the Genesis theme stores the image links on the database, you’ll need to go to a couple of WordPress tables to find them. First and foremost, you’ll need to get the ID of your WordPress post. You can easily find this by hovering over the edit link and checking the ID number.

Let’s pretend the post ID is 110. You will then need to find the meta\_value in the wp\_postmeta table.

Table: wp\_postmeta

```
meta_id     post_id   meta_key         meta_value
544         110       _thumbnail_id    45
```

```
SELECT meta_value FROM wp_postmeta WHERE meta_key='_thumbnail_id' and post_id=110;
```

The result is 45. Now that you have the meta\_value, you can then search for the link from the wp\_posts table.

Table: wp\_posts

```
ID      post_type       guid
45      attachment      http://yourdomain.com/wp-content/uploads/2017/03/featured-image.jpg
```

```
SELECT guid FROM wp_posts WHERE post_type='attachment' and id=45;
```

The result will be the URL of the image, e.g. http://yourdomain.com/wp-content/uploads/2017/03/featured-image.jpg.

It’s an odd place to store the image link, but that’s where it is.