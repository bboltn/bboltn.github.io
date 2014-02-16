---
layout: post
title: Google App Engine Development site is slow to start up
date: 2013-01-19
---

My Google App Engine development website was taking a long time to load up.  During my testing of the app, I kept uploading documents.  After a few days of testing and developing the app, I had loaded several gigs of data into my dev server.  It kept taking longer and longer to turn on.


I didn't need the data and this simple fix cleared my datastore and made the startup nice and snappy.  You might want to occasionally do this if you notice a slow start up time.

{% highlight bash %}
devappserver.py --cleardatastore myapp
{% endhighlight %}