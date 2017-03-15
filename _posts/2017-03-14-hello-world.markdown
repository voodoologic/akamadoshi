---
layout: post
title: "Hello World!"
date: 2017-03-14T23:17:30-07:00
tags:
  - octopress
  - jekyl
---

I'm making this blog with [Octopress 3](http://octopress.org/) and [Jekyll](http://jekyllrb.com/).
It's being hosted on an S3 bucket in AWS.

Already had some complications with Jekyll.
Firstly, I have no idea what I'm doing.
The relationship of how themes relate to the application
aren't all that clear. If you're theme has jekyll-paginate
code in it, it will break your build as it did with mine using
the jekyll-them-lanyon gem with the latest version of Jekyll.

It complained,
**"Pagination is enabled, but I couldn't find an index.html page to use as the pagination template. Skipping pagination"**

The remedy is to change the line:

`{{ "{% for post in paginator.posts " }}%}`

with:

`{{ "{% for post in site.posts " }}%}`

Once that was completed, I removed the pagination links from my home.html
overide file. Octopress deploy for S3 was pretty straight forward -- 
 That's the part I'm going to enjoy moving forward.

