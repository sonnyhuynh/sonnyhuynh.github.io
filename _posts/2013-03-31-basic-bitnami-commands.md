---
layout: post
permalink: /basic-bitnami-commands/
comments: true

title: Basic Bitnami Commands
description: Quick reference for basic Bitnami stack commands
date: 2013-03-31 07:45 PM

categories: notes
tags: coding basics

published: true
---

### Stack Services

What services are in this stack that I can start and stop
{% highlight bash %}
$ ./ctlscript.sh help
{% endhighlight %}

Manage all stack services
{% highlight bash %}
$ ./ctlscript.sh start
$ ./ctlscript.sh restart
$ ./ctlscript.sh stop
$ ./ctlscript.sh status
{% endhighlight %}

Manage specific stack service
{% highlight bash %}
$ ./ctlscript.sh start [service]
$ ./ctlscript.sh restart [service]
$ ./ctlscript.sh stop [service]
$ ./ctlscript.sh status [service]
{% endhighlight %}

_Examples_
{% highlight bash %}
$ ./ctlscript.sh start apache
$ ./ctlscript.sh restart mysql
$ ./ctlscript.sh stop postgresql
$ ./ctlscript.sh status apache
{% endhighlight %}


### Bitnami Shell Environment

Load environment
{% highlight bash %}
~ $ ./use_[stack]
~ $ . scripts/setenv.sh
{% endhighlight %}

_**Examples**_

_Django Stack_
{% highlight bash %}
$ ./use_djangostack
{% endhighlight %}

_Node.js Stack_
{% highlight bash %}
$ ./use_nodejs
{% endhighlight %}

_Wordpress Stack_
{% highlight bash %}
$ ./use_wordpress
{% endhighlight %}

Exit environment
{% highlight bash %}
$ exit
{% endhighlight %}


### More Information

- Bitnami Website | [bitnami.org](https://bitnami.org)
- Bitnami Documentation | [wiki.bitnami.org](https://wiki.bitnami.org)