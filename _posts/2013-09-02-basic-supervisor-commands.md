---
layout: post
permalink: /basic-supervisor-commands/
comments: true

title: Basic Supervisor Commands
description: Quick reference for basic Supervisor commands
date: 2013-09-02 11:34 AM

categories: notes
tags: coding basics

published: true
---

> **Tip:** Use [Supervisor](https://supervisord.org/) in conjunction with [Celery](https://www.celeryproject.org/) for automated or asynchronous goodness for your Django apps!

Install
{% highlight bash %}
$ easy_install supervisor
{% endhighlight %}

Create `supervisord.conf` file
{% highlight bash %}
$ echo_supervisord_conf > supervisord.conf
{% endhighlight %}

Start supervisor using `supervisord.conf`
{% highlight bash %}
$ supervisord -c supervisord.conf
{% endhighlight %}

> **Tip:** After starting supervisor, it's much easier to manage supervisor with `supervisorctl`. Run `supervisorctl help` for the list of commands.

Stop supervisor
{% highlight bash %}
$ supervisorctl shutdown
{% endhighlight %}

Check which processes are running
{% highlight bash %}
$ supervisorctl status
{% endhighlight %}

Update `supervisord` to use modified `supervisord.conf`
{% highlight bash %}
# Always run this after modifying `supervisord.conf`
$ supervisorctl update
{% endhighlight %}

### More Information
- Supervisor: A Process Control System | [supervisord.org](https://supervisord.org/)