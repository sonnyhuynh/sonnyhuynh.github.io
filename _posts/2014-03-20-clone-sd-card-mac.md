---
layout: post
permalink: /coding/clone-sd-card-mac
comments: true

title: "Clone SD Card (Mac)"
description: "How to clone an SD card on Mac"
date: 2014-03-20 08:33 PM

categories: guides
tags: coding mac pi

published: true
---

Here's how to clone an SD card on a Mac. Useful when you want to backup and restore your [Raspberry Pi](http://www.raspberrypi.org/).

**Find path to SD card**
{% highlight bash %}
$ diskutil list
{% endhighlight %}

_Should be something like `/dev/disk1`, depending on what other devices you have connected to your system_


### Make image of SD card

{% highlight bash %}
$ sudo dd if=[sd card path] of=[image].dmg
{% endhighlight %}

_Example_
{% highlight bash %}
$ sudo dd if=/dev/disk1 of=~/Desktop/backup.dmg
{% endhighlight %}

> **Tip:** During `dd` operations, hit `[ctrl] + t` to check transfer status


### Transfer image to SD card

_This will take much longer than making an image, since you are writing to an SD card, so grab a drink!_

> **Caution:** Double check input and output disk paths before running copy commands

{% highlight bash %}
~ $ diskutil unmountDisk [sd card path]
~ $ sudo dd if=[image file] of=[sd card path]
{% endhighlight %}

_Example_
{% highlight bash %}
$ sudo dd if=~/Desktop/backup.dmg of=/dev/disk2
{% endhighlight %}


### Storing images

_Image clones can be huge files, so compressing them will help save HD space!_

**Compress image**
{% highlight bash %}
$ gzip [image file]
{% endhighlight %}

**Uncompress image**
{% highlight bash %}
$ gzip -d [compressed image file]
{% endhighlight %}

