---
layout: post
permalink: /why-i-switched-to-jekyll
comments: true

title: Why I switched from WordPress to Jekyll
date: 2013-08-27 04:30 PM

categories: rants
tags: jekyll github

published: true
---

My web hosting provider, [Hostlatte](https://www.hostlatte.com/) was down for over a week. After they resolved their issues, they restored my site to their backup from before I launched this blog. I provided them with a functional local backup copy of the entire blog that I (thankfully) generated before they went down, and it took them a few tries to get the restore correct.

After the restore, the blog was still suffering from WordPress database connection issues, which I believe was due to the hosting provider still being wonky. I have restored using the backup copy I provided Hostlatte, so the restore should have worked. At this point, my patience and confidence was wearing thin, so I decided I wanted to switch providers.

And so, I stumbled upon a simple static blog generator, [Jekyll](http://jekyllrb.com/). Neat thing is [GitHub Pages](http://pages.github.com/) provides **free** hosting that happens to include Jekyll support!

So in an afternoon, I was able to do the following:

- Research and install Jekyll
- Decide if Jekyll was the right tool for the job
- Setup Jekyll development environment
- Migrate from WordPress
- Setup on GitHub Pages
- Setup custom domain for GitHub Pages

The entire setup process is fairly well-documented, including a very straightforward conversion process from WordPress.

Simple, done, painless. [Blog RELAUNCHED!]({{ site.url }}/blog-relaunch)