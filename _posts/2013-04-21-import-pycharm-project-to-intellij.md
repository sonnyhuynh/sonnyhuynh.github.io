---
layout: post
permalink: /import-pycharm-project-to-intellij
comments: true

title: Import a PyCharm Project to IntelliJ IDEA
description: How to import a PyCharm 2.7.1 project to IntelliJ IDEA 12.1.1 for Mac
date: 2013-04-21 06:37 PM

categories: guides
tags: coding apps django python intellij pycharm

published: true
---

Since my recent purchase of JetBrains' IntelliJ IDEA, I've had to move my PyCharm 2.7.1 projects to IntelliJ IDEA 12.1.1 on my Mac. The process isn't as smooth as it should be, so here's a short guide on the migration.

<!--more Check it out after the jump!-->


### Before you begin

You need to have:
- PyCharm 2.7.1 Django project
- IntelliJ IDEA 12.1.1 for Mac

<small>If you're using a different version/OS, please be aware that the steps/screenshots may differ from this guide.</small>

This walkthrough's Django project structure:

{% highlight bash %}
- project_name
	- project_name/
		- settings.py
	- templates/
	- manage.py
{% endhighlight %}

<small>If your project structure is different, there may be more/less configurations required during the migration.</small>


### Create a new project

1. Create a New Project in IntelliJ IDEA

	![Create a New Project in IntelliJ IDEA]({{ site.images }}{{ page.url }}/pycharm_to_intellij_01.png "Create a New Project in IntelliJ IDEA")

2. Under `Python`, click `Python Module`.

3. Select the existing PyCharm project directory for `Project location`. Click `Next`

	![Select the existing PyCharm project directory for 'Project location']({{ site.images }}{{ page.url }}/pycharm_to_intellij_02.png "Select the existing PyCharm project directory for 'Project location'")

4. Click `Yes` when prompted to overwrite the existing `.idea` directory


### Add the Python environment

1. Click `Configure...`
2. In the `Configure SDK` window, click `[+]`
3. In the `Add New SDK` dropdown, click `Python SDK`

	![In the 'Add New SDK' dropdown, click 'Python SDK']({{ site.images }}{{ page.url }}/pycharm_to_intellij_03.png "In the 'Add New SDK' dropdown, click 'Python SDK'")

4. In the `Select Interpreter Path` dropdown, click `Local...`

	![In the 'Select Interpreter Path' dropdown, click 'Local...']({{ site.images }}{{ page.url }}/pycharm_to_intellij_04.png "In the 'Select Interpreter Path' dropdown, click 'Local...'")

5. Select the `bin/python2.7` file of the project's Python interpreter. Click `OK`

	![Select the 'bin/python2.7' file of the project's Python interpreter]({{ site.images }}{{ page.url }}/pycharm_to_intellij_05.png "Select the 'bin/python2.7' file of the project's Python interpreter")

6. Click `Next`.


### Enable the Django library

1. Select `Django`. Click `Finish`

	![Select 'Django']({{ site.images }}{{ page.url }}/pycharm_to_intellij_06.png "Select 'Django'")


### Edit the project settings</h4>

1. Go to `File` -&gt; `Project Structure`

	![Go to 'File' - 'Project Structure']({{ site.images }}{{ page.url }}/pycharm_to_intellij_07.png "Go to 'File' - 'Project Structure'")

2. Under `Project Settings` -&gt; `Project`, select the project's Python interpreter created earlier in the `Project SDK` dropdown.

	![Select the project's Python interpreter created earlier in the 'Project SDK' dropdown]({{ site.images }}{{ page.url }}/pycharm_to_intellij_08.png "Select the project's Python interpreter created earlier in the 'Project SDK' dropdown")

3. Under `Project Settings` -&gt; `Modules` -&gt; `Django`, select the existing project's `settings.py` file for `Settings`

	![Select the existing project's 'settings.py' file for 'Settings']({{ site.images }}{{ page.url }}/pycharm_to_intellij_09.png "Select the existing project's 'settings.py' file for 'Settings'")

4. `Apply` the changes and click `OK`


# More Information

**For a more in-depth and better written guide:**

- Setting up Python Django project using IntelliJ 11 | [Rodrigos Science](http://rodrigothescientist.wordpress.com/2012/08/03/setting-up-pythondjango-project-using-intellij-11/)
