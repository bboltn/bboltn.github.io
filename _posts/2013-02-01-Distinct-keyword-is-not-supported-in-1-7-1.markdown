---
layout: post
title: Distinct keyword is not supported in 1 7 1
date: 2013-02-01
---

I've been trying to get the DISTINCT keyword working with my Google App Engine query.&nbsp; Turns out that feature isn't available in 1.7.1 which is the version I'm using.&nbsp; Upgrade to 1.7.4 to get it working.<br /><br /><blockquote>db.Query(EntityName, projection = ("entityProperty",)).run(distinct=True)<br />Unknown configuration option ('distinct')</blockquote><b>Edit</b><br />SDK 1.7.4 release notes<br />http://code.google.com/p/googleappengine/wiki/SdkReleaseNotes 
