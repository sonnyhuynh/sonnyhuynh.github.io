---
layout: post

title: Markdown on Save Improved vs WP-Markdown
description: A short review on two Markdown WordPress plugins: Markdown on Saved Improved and WP-Markdown
date: 2013-05-24 09:00 PM

categories: coding
tags: reviews

published: true
---

I was looking to write and edit my posts directly with [Markdown](http://daringfireball.net/projects/markdown/) syntax to streamline my posting workflow. I stumbled upon and tried out these two Markdown WordPress plugins: [Markdown on Save Improved](http://wordpress.org/extend/plugins/markdown-on-save-improved/) and [WP-Markdown](http://wordpress.org/extend/plugins/wp-markdown/).

<!--more Here is a quick rundown on my experience with them.-->

After a quick glance at the two plugins, the biggest difference is how the posts are accessed and stored:

- Markdown on Save Improved 
	- Converts Markdown to HTML, saves both Markdown and HTML versions
	- Edit Markdown version
- WP-Markdown
	- Converts Markdown to HTML, saves HTML version only
	- Converts HTML to Markdown for editing


### Testing

I decided to try WP-Markdown first, as saving a single copy of a post was more appealing than saving two.

After creating and modifying a few test posts, I discovered that because WP-Markdown converts the saved HTML to/from Markdown when editing/saving, there is a difference in Markdown syntax between the one before and after saving.

<p>For example, if I use underscores <code>_</code>, WP-Markdown converts them to asterisks <code>*</code>. It also converts inline links <code>[link text](link)</code> to reference links <code>[link text][link id]</code> with link definitions <code>[link id]: link</code> grouped at the bottom of the file.</p>

I prefer to write my Markdown a specific way, so having WP-Markdown change my conventions is something I found extremely irritating. This is obviously an issue of personal style, but nonetheless an issue for me.

So, I moved on to try Markdown on Save Improved. The plugin is definitely less annoying, as it didn't mess with my Markdown conventions. WIN.

Also another point I'd like to make is that WP-Markdown is slower at opening posts for editing, since it must first convert to Markdown. I'll take speed over storage right now, however that may change down the road if storage becomes an issue.


### Wrapping up

Ultimately, I decided to go with Markdown on Save Improved for its preservation of my Markdown. WP-Markdown is still pretty neat, as it has support for not only posts, but comments and BBPress forums. Not really useful for me, but thought I'd mention it, as maybe it'll be the reason you decide to go with WP-Markdown over Markdown on Save Improved.


### More Information

- Markdown | [daringfireball.net/projects/markdown/](http://daringfireball.net/projects/markdown/)
- Markdown on Saved Improved | [wordpress.org/extend/plugins/markdown-on-save-improved/](http://daringfireball.net/projects/markdown/)
- WP-Markdown | [wordpress.org/extend/plugins/wp-markdown/](http://wordpress.org/extend/plugins/wp-markdown/)
