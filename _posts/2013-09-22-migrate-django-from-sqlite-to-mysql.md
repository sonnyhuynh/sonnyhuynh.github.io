---
layout: post
permalink: /migrate-django-from-sqlite-to-mysql
comments: true

title: Migrate Django from SQLite to MySQL
description: Problems I have encountered when migrating Django applications from SQLite to MySQL
date: 2013-09-22 10:39 AM

categories: rants
tags: coding django python sqlite mysql

published: true
---

Migrating a Django application from SQLite to MySQL can be a very complex task. Thankfully, I was able to successfully perform migrations using this guide I found: [Move django from SQLite to MySQL](http://macrotoma.blogspot.com/2012/10/solved-move-django-from-sqlite-to-mysql.html).

Of course, nothing goes as smooth as it should. Here are two issues that I encountered during migrations and how I resolved them.

### `ForeignKey` relationships

Upon running the `to_slave.run()` function inside the python shell, I encountered repeated occurrences of this error:

`Cannot add or update a child row: a foreign key constraint fails`

**Calling `to_slave.run()` again resolved the issue!**

On the first run of the function, there are errors because a particular object that is being created has `ForeignKey` relationships to objects that have not been created yet. Running the function a second time allows objects that failed the first time succeed during the second. This is because the required `ForeignKey` objects have been created at this point.

I suppose this all could be resolved by optimizing the order the objects are re-created in the MySQL database, but it seemed simpler to me to just run it twice.

Also, the more complex the relationships are in the database, the more times you may have to run the `to_slave.run()` function until no longer produces any errors. At this point, optimization of the function might be necessary.

### `ManyToMany` relationships

Another issue that I ran into was with objects containing `ManyToMany` relationships. Other developers had mentioned about this in the comments of the guide, however the solution remains unclear.

When the `to_slave.run()` function runs, it does create the objects that contain `ManyToMany` relationships. The problem is that the relationships are left empty/unconnected.

**Fortunately, the databases were small enough for me to just manually reconnect these relationships without being tedious and taking much time.**

_Unfortunately, this will be a problem for larger databases, as manually reconnecting `ManyToMany` relationships in this situation is not a proper solution. I will revisit this when the situation arises._

### Final Thoughts
- Use SQLite if your app has little to no concurrency
- Switch to MySQL as early as possible, while the production database is still small/manageable. This will save you the pain of worrying about migration problems with large data sets.
- MySQL -> production, SQLite -> development