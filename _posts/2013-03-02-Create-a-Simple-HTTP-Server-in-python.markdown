---
layout: post
title: Create a Simple HTTP Server in python
date: 2013-03-02
---

### Short version:

{% highlight bash %}
python -m SimpleHTTPServer
{% endhighlight %}

### Long version:

My background is ASP.NET web development.  When I think web server, I think of big heavy programs like IIS.  I knew that there were other webservers, but I never really considered using them for development. 

At my new job, I've been doing Python + Google App Engine development (not asp.net).  This change in my career has led to a change in focus of what I read about.  I'm no longer hitting up the Microsoft C# sites anymore - not because they are bad -- just not relavent to my career.

About a week ago I came across an article from codeschool.com that talked about using node.js for a simple webserver.  This wasn't a big surprise to me -- I knew things besides IIS existed -- I had just never looked into it -- Up to this point I've just been using GAE as my webserver.

I fell into a rat hole of various ways to have mini-webservers.  Node.js had several options.  I pulled a few from [Eric Allam's blog post](https://coderwall.com/p/rbghmg) (I found it via codeschool).  If you look down in the comments you'll find other simpler options to Eric's suggestion.  It went like this:

"You can using the filed module, but really Express is a better way to go, then again the connect module is the module actually serving the content in Express.  Looks like I've got options.  Then again, I'm really just interested in learning Python at the moment, I wonder if they have something? Sure enough - SimpleHTTPServer is the answer."

Nothing to do with Node.js, but that's how brainstorming and research goes.
