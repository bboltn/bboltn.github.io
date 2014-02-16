---
layout: post
title: Finished move to dedicated server
date: 2010-03-01
---

Picstogo.net ran on a shared hosting platform from October 30th to March 1st. Shared hosting just did not cut it. Not much of a surprise really considering what we did.

We were uploading 400 files at around 2-3MB each, zipping them up, and downloading this 1GB+ file. Once that finished, we'd run the process again, but in the other direction.

Shared hosting imploded with this demand.

My client sprung for the dedicated server plan back in January. I spent the month doing research and getting a good deal. We decided to go with [Rackmounted](http://www.rackmounted.com/). They offered a few things others didn't for the price:

1. Windows 2008
2. Inexpensive backup
3. No setup fee

The past month I've setup SMTP, FTP, ASP.NET MVC, IIS, SQL, DNS, and a few other acronyms. The migration was officially done as of this morning when the last bit of DNS finally pointed to the new IP.

The server is much faster than shared hosting. Page load and download speed are noticeable faster. I am downloading at 700Kb. Considering this site is all about download and upload, that's a big improvement for customers.