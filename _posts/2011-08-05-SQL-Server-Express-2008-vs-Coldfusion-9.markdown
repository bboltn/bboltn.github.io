---
layout: post
title: SQL Server Express 2008 vs Coldfusion 9
date: 2011-08-05
---

I spent 4 hours trying to get Coldfusion 9 to make a datasource that connects to SQL Server Express 2008. &nbsp;It kept erroring out. &nbsp;<a href="http://www.google.com/search?rlz=1C1CHFX_enUS430US430&amp;sourceid=chrome&amp;ie=UTF-8&amp;q=Coldfusion+9+to+make+a+datasource+to+connect+to+SQL+Server+Express+2008&amp;safe=active">It looks like many people run into similar issues.</a><br /><br />A few bloggers and forum posters said to try the following:<br /><br /><ol><li>enable TCP connections for your sql agent</li><li>Make sure SQL Server is running</li><li>make sure sql authentication is turned on</li><li>update to the latest JDBC driver</li><li>Turn off your firewall</li></ol><div>Yeah, I tried those things. &nbsp;They didn't fix a thing. &nbsp;Here's what does work:</div><div><ol><li>DON'T USE SQL SERVER EXPRESS</li><li>Get a real copy of SQL Server</li><li>Done</li></ol><div>Nothing wrong with SQL Server Express. &nbsp;I've used it on other projects. &nbsp;The real problem is that Coldfusion and Microsoft products don't normally work well with each other.</div><div><br /></div></div>
