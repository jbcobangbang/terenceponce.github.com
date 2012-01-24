---
layout: post
title: "Optional Arguments, a gift from heaven"
date: 2010-11-01 12:00:00
category: programming
tags:
 - Python
---

I’ve been messing around with functions in Python. One neat feature that I came across are optional arguments. Here’s some code that I’ve written to explain more about optional arguments:

{% highlight python tabsize=2 %}
def foo(length, bar = 5, foobar = 10):
  """A sample function demonstrating optional arguments.

  Takes 3 integer objects as its arguments"""
  print "Length is %d\nBar is %d\nFoobar is %d\n" % (length, bar, foobar)
{% endhighlight %}

As with any other language out there, you can set default values for certain arguments in case they aren’t mentioned in a function call. For the above function, the value for **bar** will be 5 and 10 for **foobar** if the function was called like this:

{% highlight python %}
foo(someInteger)
{% endhighlight %}

Two other ways of calling function foo are:

{% highlight python %}
foo(someInteger, bar = 3)
{% endhighlight %}

{% highlight python %}
foo(someInteger, bar = 3, foobar = 7)
{% endhighlight %}

The above function calls will override the default values for the specified argument.

Now what if you want to override the value for **foobar** but leave **bar** unchanged when calling the function? In most, if not all, language that I know, you’ll just end up doing some workaround to achieve the effect that you want. On the other hand, Python makes it possible out of the box:

{% highlight python %}
foo(someInteger, foobar = 7)
{% endhighlight %}

I’m pretty sure this will come in handy in the future. This is also one of the coolest features I found so far.

