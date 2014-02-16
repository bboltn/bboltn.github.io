---
layout: post
title: Distinct keyword is not supported in 1 7 1
date: 2013-02-01
---

I've been trying to get the DISTINCT keyword working with my Google App Engine query.  Turns out that feature isn't available in 1.7.1 which is the version I'm using.  Upgrade to 1.7.4 to get it working.

{% highlight python %}
db.Query(EntityName, projection = ("entityProperty",)).run(distinct=True)
Unknown configuration option ('distinct')
{% endhighlight %}

### Edit

[SDK 1.7.4 release notes](http://code.google.com/p/googleappengine/wiki/SdkReleaseNotes)
