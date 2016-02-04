---
layout: post
permalink: /basic-postgresql-commands/
comments: true

title: Basic PostgreSQL Commands
description: Quick reference for basic PostgreSQL commands
date: 2013-04-14 06:24 PM

categories: notes
tags: coding basics

published: true
---

Connect
{% highlight bash %}
$ psql -h [hostname] -p [port]
# Default port: 543
{% endhighlight %}

_Example_
{% highlight bash %}
$ psql -h localhost
{% endhighlight %}

Create DB
{% highlight bash %}
$ CREATE DATABASE [database_name];
{% endhighlight %}

Delete DB
{% highlight bash %}
$ DROP DATABASE [database_name];
{% endhighlight %}

Disconnect
{% highlight bash %}
$ \q
{% endhighlight %}