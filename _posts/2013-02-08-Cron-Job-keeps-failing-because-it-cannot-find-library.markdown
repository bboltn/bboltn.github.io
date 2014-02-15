---
layout: post
title: Cron Job keeps failing because it cannot find library
date: 2013-02-08
---

I had a cron job that kept failing in google app engine.&nbsp; This wasn't a production environment, but it was an appspot.&nbsp; Turns out the fix was pretty simple.&nbsp; Use Target in the cron.yaml to specify which version you want to run against.&nbsp; If you don't, it just runs against the default version.&nbsp; The default version doesn't have the code that the cron job was referencing so it fails.&nbsp; The other fix is to just set your version to the default version.<br /><br /><a href="https://developers.google.com/appengine/docs/python/config/cron#About_cron_yaml">https://developers.google.com/appengine/docs/python/config/cron#About_cron_yaml</a><br /><br /><br />
