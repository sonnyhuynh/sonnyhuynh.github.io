---
layout: post
comments: true

title: "SSH without a Password"
description: "How to SSH into a server without entering a password"
date: 2014-05-21 06:26 PM

categories: guides
tags: coding productivity

published: true
---

Entering passwords is really annoying if you SSH into servers on a regular basis. Here's how to add your SSH key to the remote host so you no longer have to do so!

<ol>
    <li>Start on your local machine (the machine you use to tap into the remote host)</li>
    <li><p>Copy <code>id_rsa.pub</code> to home directory of remote host</p>
        {% highlight bash %}
$ scp ~/.ssh/id_rsa.pub [user]@[remote hostname]:~
{% endhighlight %}
    </li>
    <li><p>SSH into server and enter password. Celebrate that this will be the last time you will need to do this.</p>

        {% highlight bash %}
$ ssh [user]@[remote hostname]
{% endhighlight %}
    </li>
    <li><p>Add <code>id_rsa.pub</code> to <code>authorized_keys</code></p>

        {% highlight bash %}
$ cat ~/id_rsa.pub >> ~/.ssh/authorized_keys
{% endhighlight %}
    </li>
    <li><p>Remove <code>id_rsa.pub</code> and exit remote server</p>

        {% highlight bash %}
~ $ rm ~/id_rsa.pub
~ $ exit
{% endhighlight %}
    </li>
    <li><p>Test it! You should no longer be prompted to enter a password!</p>

        {% highlight bash %}
$ ssh [user]@[remote hostname]
{% endhighlight %}
    </li>
</ol>

> There are alot of assumptions made in this guide, so if you run into problems, the [Ubuntu Community Wiki](https://help.ubuntu.com/community/SSH/OpenSSH/Keys) is very helpful for troubleshooting!