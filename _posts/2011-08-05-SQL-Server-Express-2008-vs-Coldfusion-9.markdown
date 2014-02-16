---
layout: post
title: SQL Server Express 2008 vs Coldfusion 9
date: 2011-08-05
---

I spent 4 hours trying to get Coldfusion 9 to make a datasource that connects to SQL Server Express 2008.  It kept erroring out.  [It looks like many people run into similar issues.](http://www.google.com/search?rlz=1C1CHFX_enUS430US430&sourceid=chrome&ie=UTF-8&q=Coldfusion+9+to+make+a+datasource+to+connect+to+SQL+Server+Express+2008&safe=active)

A few bloggers and forum posters said to try the following:

1. enable TCP connections for your sql agent
2. Make sure SQL Server is running
3. make sure sql authentication is turned on
4. update to the latest JDBC driver
5. Turn off your firewall

Yeah, I tried those things.  They didn't fix a thing.  Here's what does work:

1. DON'T USE SQL SERVER EXPRESS
2. Get a real copy of SQL Server
3. Done

Nothing wrong with SQL Server Express.  I've used it on other projects.  The real problem is that Coldfusion and Microsoft products don't normally work well with each other.
