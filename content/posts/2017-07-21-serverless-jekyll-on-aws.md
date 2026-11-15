---
title: 'serverless jekyll on aws'
author: ulysses

date: 2017-07-21
slug: serverless-jekyll-on-aws
draft: false
---

I recently started playing around with [Jekyll](https://jekyllrb.com/).

Jekyll is a flat-file CMS that doesn’t need a database. You don’t even need to know HTML to work with it. You just write your content using the Markdown language on any text editor. Once you’re done editing, you run “jekyll build” and Jekyll takes care of the rest. Since Jekyll files are stored on flat-files, you have quite a few choices where to host your website. You can host it on just about any hosting provider. You can have it hosted on [Github](http://github.com) for free, or better yet can run it as a serverless website on [Amazon S3](https://aws.amazon.com/s3/). Serverless meaning, it’s not running on a web server since S3 can host static files. In addition, you can take advantage of [Cloudfront](https://aws.amazon.com/cloudfront/?nc2=h_m1) for its content distribution to speed up your website, and give it high availability.

So, here’s a [demo](http://ulyssesronquillo.com/) of Jekyll running on AWS S3 and Cloudfront.

You can learn more about Jekyll by visiting their [website](https://jekyllrb.com/).