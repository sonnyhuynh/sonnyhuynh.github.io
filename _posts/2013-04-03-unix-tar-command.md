---
layout: post

title: Unix Tar Command
date: 2013-04-03 06:59 PM

categories: coding
tags: basics

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

- The Ultimate Tar Command Tutorial with 10 Practical Examples @ The Geek Stuff | [www.thegeekstuff.com/2010/04/unix-tar-command-examples/](http://www.thegeekstuff.com/2010/04/unix-tar-command-examples/)