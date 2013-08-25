--- 
layout: post

title: Useful Git Commands
date: 2013-03-21 10:31 PM

categories: coding
tags: basics

published: true
---

### Working with &#8217;origin&#8217; Remote Branch

_NOTE: The name of my remote branch is called `origin`. Substitute `origin` for name of remote branch you are working with._

Push current branch to repo
{% highlight bash %}
$ git push
{% endhighlight %}

Push branch to &#8217;origin&#8217; repo
{% highlight bash %}
$ git push origin [branch]
{% endhighlight %}

Remove branch from &#8217;origin&#8217; repo
{% highlight bash %}
$ git push origin :[branch]
{% endhighlight %}

Pull new branch from &#8217;origin&#8217; repo, create new local
{% highlight bash %}
$ git checkout -b [local_branch] origin/[remote_branch]
{% endhighlight %}

Pull branch changes from &#8217;origin&#8217; repo, merge with current branch
{% highlight bash %}
$ git pull origin [branch]
{% endhighlight %}


### Stashes

Add
{% highlight bash %}
$ git stash
{% endhighlight %}

Use Latest
{% highlight bash %}
$ git stash pop
{% endhighlight %}

Show
{% highlight bash %}
$ git stash list
{% endhighlight %}

Use Specific Stash
{% highlight bash %}
$ git stash apply stash@{[index]}
{% endhighlight %}

Delete Specific Stash
{% highlight bash %}
$ git stash drop stash@{[index]}
{% endhighlight %}


### Uncategorized

Modify last commit
{% highlight bash %}
# do NOT use if commit has been pushed to remote.
$ git commit --amend -m '[message]'
{% endhighlight %}

Tagging
{% highlight bash %}
$ git tag -a [tag name] -m '[tag message]'
{% endhighlight %}

Revert specific commit
{% highlight bash %}
$ git revert [commit]
{% endhighlight %}


### More Information

- Pro Git by Scott Chacon (FREE online book) | [git-scm.com/book](http://git-scm.com/book)
- Git Website | [git-scm.com](http://git-scm.com)