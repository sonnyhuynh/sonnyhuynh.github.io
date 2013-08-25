---
layout: post

title: Migrating between PostgreSQL Databases
date: 2013-05-15 08:07 PM

categories: coding
tags: postgresql

published: true
---

Here's how to move from one PostgreSQL DB to another PostgreSQL DB.

Some uses for this could include:

- Creating backups
- Cloning a production DB to a development DB for debugging

Export
{% highlight bash %}
$ pg_dump [database_name] > [import_file]
{% endhighlight %}

_Example_
{% highlight bash %}
$ pg_dump my_postgres_db > dump.sql
{% endhighlight %}

Import
{% highlight bash %}
$ psql [database_name] < [import_file]
{% endhighlight %}

_Example_
{% highlight bash %}
$ psql my_postgres_db < dump.sql
{% endhighlight %}