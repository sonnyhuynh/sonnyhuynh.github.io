---
layout: post
permalink: /basic-south-commands
comments: true

title: Basic South Commands
description: Quick reference for basic Django South commands
date: 2013-05-01 06:55 PM

categories: notes
tags: coding basics django python

published: true
---

Initial Migration
{% highlight bash %}
$ python manage.py schemamigration [app] --initial
{% endhighlight %}

Add Migration
{% highlight bash %}
$ python manage.py schemamigration [app] --auto
{% endhighlight %}

Apply Migration
{% highlight bash %}
$ python manage.py migrate [app]
{% endhighlight %}

Convert existing DB to South
{% highlight bash %}
~ $ python manage.py syncdb
~ $ python manage.py convert_to_south [app]
{% endhighlight %}

### More Information
- South Website | [south.aeracode.org](http://south.aeracode.org/)