---
layout: post
permalink: /basic-virtualenv-commands/
comments: true

title: Basic Virtualenv Commands
description: Quick reference for basic virtualenv commands
date: 2013-03-24 05:38 PM

categories: notes
tags: coding basics python

published: true
---

Activate virtualenv
{% highlight bash %}
$ source [environment dir]/bin/activate
{% endhighlight %}

Deactivate virtualenv
{% highlight bash %}
$ deactivate
{% endhighlight %}

Create requirements.txt
{% highlight bash %}
~ $ source [environment dir]/bin/activate
~ $ pip freeze > requirements.txt
~ $ deactivate
{% endhighlight %}


Install new environment from requirements.txt
{% highlight bash %}
~ $ source [environment dir]/bin/activate
~ $ pip install -r requirements.txt
~ $ deactivate
{% endhighlight %}

Create new virtualenv with distribute
{% highlight bash %}
$ virtualenv --distribute [environment dir]
{% endhighlight %}

### More Information

- Official virtualenv documentation | [virtualenv.org](http://www.virtualenv.org)