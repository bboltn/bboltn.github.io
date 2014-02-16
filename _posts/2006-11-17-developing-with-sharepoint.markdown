---
layout: post
title: developing with sharepoint
date: 2006-11-17
---

I work with a product from Microsoft called Sharepoint. It is a document management/company portal. Sharepoint has a large API that you can use to interact with programmatically. Some of this API is in the form of services accessible only from the server and others are exposed as web services.

Initially I started working with the API services. You can access these API services through 3 ways. Either in web parts, apps running on the server or non-compiled aspx web pages sitting in a special layouts folder.

First I decided to create web parts. After creating two web parts, we realized it was too much trouble to troubleshoot and install. There was also a really long wait to install web parts. They required a IIS restart and we couldn't restart IIS but once a month. Because we didn't want to wait that long we started thinking of other ways to use sharepoint.

Next we started calling sharepoint web services from javascript. The great thing about this is javascript pages can be loaded into sharepoint immediately. No wait. So now we can interact with sharepoint AND not have a long wait to install. There are downsides. The Webservices aren't as powerful as the services. So there are still some things we can't do well, like permissions.

Then we come about using the non-compiled aspx pages in our special layouts folder. Here we can put code into a special folder and only have to wait a week for an install. This seemed to be the best so far, however since it's not compiled we can't debug with Visual Studio or get any useful syntax error messages. Syntax errors all say "External component caused an error."

Of all these choice we decided on the last for most of our projects.

But it was good that I learned the previous two because everything can be combined into one big happy sharepoint family.

My latest project was actually very cool and combined most of the previous techniques and some computer science theory.

Until next time...
