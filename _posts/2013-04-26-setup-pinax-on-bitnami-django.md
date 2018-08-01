---
layout: post
permalink: /setup-pinax-on-bitnami-django/
comments: true

title: Setting up pinax-project-account on Bitnami Django Stack for Mac/Linux
description: Walkthrough on how to install a Bitnami Django 1.4.5 stack on Mac/Linux and then setup + deploy the pinax-project-account starter project to the stack
date: 2013-04-26 06:11 PM

categories: guides
tags: coding django python bitnami pinax

published: true
---

Wrote a walkthrough to show you how to install a [Bitnami Django 1.4.5](https://bitnami.com/stack/django) stack on a Mac or Linux box and then setup + deploy the [pinax-project-account](https://github.com/pinax/pinax-project-account) Django starter project with a newly created sqlite3 DB that can be accessed at `localhost:8080`.

<!--more Check it out after the jump!-->


### Before you begin

Download the [Bitnami Django native installer](https://bitnami.com/stack/django/installer) for your system.

<small>This walkthrough uses the Bitnami Django 1.4.5 native installer. If you're using a different version, please be aware that the steps may differ from this guide.</small>


### Install the native Bitnami stack

**Installation Notes**

- For this example, only sqlite3 and Django are required. By only selecting what's necessary, installing the stack will go much faster, however there is no harm in installing more than what's necessary except for your patience.
- Do not setup an initial project.

#### On Linux

{% highlight bash %}
$ ./[bitnami native installer]
{% endhighlight %}

#### On Mac

Run the native installer `.dmg`


### Inside the stack environment

**Step 1:** Open a shell environment or Terminal (<a href="https://www.iterm2.com/">iTerm2</a>!)

{% highlight bash %}
$ cd [stack location]
{% endhighlight %}

**Step 2:** Activate the stack environment

{% highlight bash %}
- $ ./use_djangostack
- $ . scripts/setenv.sh
{% endhighlight %}

**Step 3:** Create a new pinax accounts project

{% highlight bash %}
- $ cd [stack location]/apps/django/django_projects/
- $ django-admin.py startproject --template=https://github.com/pinax/pinax-project-account/zipball/master [project_name]
{% endhighlight %}

**Step 4:** Check to see if pip is installed

{% highlight bash %}
$ which pip
{% endhighlight %}

**IF** the path does _**NOT**_ point to `[stack location]/python/bin/pip`

**THEN** pip is _**NOT**_ installed. Run `easy_install pip` to install pip.

**Step 5:** Install required packages from requirements.txt

{% highlight bash %}
- $ cd [project_name]
- $ pip install -r requirements.txt
{% endhighlight %}

**Step 6:** Collect the static files

{% highlight bash %}
$ python manage.py collectstatic
{% endhighlight %}

Enter `yes` when prompted

_Make note of the full path of the static files. You will need this for the next step. By default it should be at_

{% highlight bash %}
[stack location]/apps/django/django_projects/[project_name]/[project_name]/site_media/static
{% endhighlight %}

**Step 7:** Create the sqlite3 database file

{% highlight bash %}
$ python manage.py syncdb
{% endhighlight %}


### Edit settings.py

**Step One:** Open `settings.py` in a text editor. It is located at
{% highlight bash %}
[stack location]/apps/django/django_projects/[project_name]/[project_name]/settings.py
{% endhighlight %}

**Step Two:** Set default database name to the full path of the database created in the previous step.

_Replace_
{% highlight python %}
DATABASES = {
    "default": {
    "ENGINE": "django.db.backends.sqlite3",
    "NAME": "dev.db",
    }
}
{% endhighlight %}

_With_
{% highlight python %}
DATABASES = {
    "default": {
    "ENGINE": "django.db.backends.sqlite3",
    "NAME": "[stack location]/apps/django/django_projects/[project_name]/dev.db",
    }
}
{% endhighlight %}


### Edit django.conf

**Step One:** Open `django.conf` in a text editor. It is located at

{% highlight bash %}
[stack location]/apps/django/conf/django.conf
{% endhighlight %}

**Step Two:** Modify Django app URL from `localhost:8080/Project` to `localhost:8080`

_Replace_
{% highlight python %}
WSGIScriptAlias /Project
{% endhighlight %}

_With_
{% highlight python %}
WSGIScriptAlias /
{% endhighlight %}

**Step Three:** Modify location to static file directory

_Replace_
{% highlight python %}
Alias /static "[stack location]/apps/django/lib/python2.7/site-packages/django/contrib/admin/static"
{% endhighlight %}

_With_
{% highlight python %}
Alias /site_media/static "[stack location]/apps/django/django_projects/[project_name]/[project_name]/site_media/static"
{% endhighlight %}

_Replace_
{% highlight python %}
<Directory '[stack location]/apps/django/lib/python2.7/site-packages/django/contrib'>
{% endhighlight %}

_With_
{% highlight python %}
<Directory '[stack location]/apps/django/django_projects/[project_name]/[project_name]/site_media/static'>
{% endhighlight %}


### Edit django.wsgi

**Step One:** Open `django.wsgi` in a text editor. It is located at

{% highlight bash %}
[stack location]/apps/django/scripts/django.wsgi
{% endhighlight %}

**Step Two:** Modify location to Django project directory

_Replace_
{% highlight python %}
sys.path.append('[stack location]/apps/django/django_projects/Project')
{% endhighlight %}

_With_
{% highlight python %}
sys.path.append('[stack location]/apps/django/django_projects/[project_name]')
{% endhighlight %}

**Step Three:** Modify location to Django project settings

_Replace_
{% highlight python %}
os.environ['DJANGO_SETTINGS_MODULE'] = 'Project.settings'
{% endhighlight %}

_With_
{% highlight python %}
os.environ['DJANGO_SETTINGS_MODULE'] = '[project_name].settings'
{% endhighlight %}


### Restart Apache

To commit the changes made up to this point, Apache must be restarted

{% highlight bash %}
$ ./ctlscript.sh restart apache
{% endhighlight %}

Your app can be found at `localhost:8080`

### More Information

- Bitnami Django Stack | [bitnami.com/stack/django](https://bitnami.com/stack/django)
- Django Website | [djangoproject.com](https://www.djangoproject.com/)