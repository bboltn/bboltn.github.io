---
layout: post
title: Cron Job keeps failing because it cannot find library
date: 2013-02-08
---

I had a cron job that kept failing in google app engine.  This wasn't a production environment, but it was an appspot.  Turns out the fix was pretty simple.  Use Target in the cron.yaml to specify which version you want to run against.  If you don't, it just runs against the default version.  The default version doesn't have the code that the cron job was referencing so it fails.  The other fix is to just set your version to the default version.

[https://developers.google.com/appengine/docs/python/config/cron#Aboutcronyaml](https://developers.google.com/appengine/docs/python/config/cron#Aboutcronyaml)