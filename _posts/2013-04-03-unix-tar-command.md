---
layout: post
permalink: /unix-tar-command/
comments: true

title: Unix Tar Command
description: Quick reference for the Unix `tar` command
date: 2013-04-03 06:59 PM

categories: notes
tags: coding basics

published: true
---

### Create

uncompressed
{% highlight bash %}
$ tar cvf [archive].tar [directory]
# c - create new archive
# v - verbose
# f - next argument is archive file name [archive]
{% endhighlight %}

gzip
{% highlight bash %}
$ tar cvzf [archive].tar.gz [directory]
{% endhighlight %}

bzip2
{% highlight bash %}
$ tar cvjf [archive].tar.bz2 [directory]
{% endhighlight %}

gzip vs bzip2

- bzip2 more time to compress/decompress
- bzip2 smaller size


### Extract

uncompressed
{% highlight bash %}
$ tar xvf [archive]
# x - extract
{% endhighlight %}

gzip
{% highlight bash %}
$ tar xvzf [archive]
{% endhighlight %}

bzip2
{% highlight bash %}
$ tar xvjf [archive]
{% endhighlight %}


### More Information

- The Ultimate Tar Command Tutorial with 10 Practical Examples @ The Geek Stuff | [www.thegeekstuff.com/2010/04/unix-tar-command-examples/](https://www.thegeekstuff.com/2010/04/unix-tar-command-examples/)