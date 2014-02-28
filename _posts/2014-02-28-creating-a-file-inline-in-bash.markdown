---
layout: post
title: Creating a file inline in Bash
date: 2014-02-28
---

By necessity and sometimes by choice, I've been using the command prompt more in Mac OS X.  I found this handy trick to create files on the command line.

{% highlight bash %}
cat > filename << EOF
The contents
of your file 
go here.
EOF
{% endhighlight %}

You can replace EOF with any string that signifies the end of your file.  EOF is a good choice because it should not appear inside of the file contents.
