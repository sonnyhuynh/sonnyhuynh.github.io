---
layout: post
comments: true

title: "Dashboard Widgets Mysteriously Disappeared"
description: "Can't add Dashboard widgets because they randomly disappeared? Here's what I did to fix it!"
date: 2014-04-17 06:11 PM

categories: guides
tags: mac

published: true
---

Ever try adding a new Dashboard widget like Stickies, only to find that all the widgets are gone?

Make sure the widgets exist in `/Library/Widgets` and/or `~/Library/Widgets` and then try resetting Launchpad's Database via Terminal:

{% highlight bash %}
$ rm ~/Library/Application\ Support/Dock/*.db ; killall Dock
{% endhighlight %}

_This worked for me on Mac OS X Mavericks 10.9.2, however it should work on Lion/Mountain Lion also. Post a comment if it worked for you on a different version!_