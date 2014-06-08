---
layout: post
title: 2nd Annual National Day of Civic Hacking
date: 2014-06-08
---

Last weekend, May 31th - June 1st, [Geoffrey Shoultz](mailto:silverag47@gmail.com), [Patrick Smith](mailto:mpatricks@gmail.com), and I competed in the local "National Day of Civic Hacking." Our app
was called "Let Your Voice Be Heard."  If you want to get in touch with your senator, your mayor, find out where to vote, or how to register
to vote, then this is your app. Let your voice be heard!

It's a mobile app that lets you look up your local, state, and national officials.  It also shows
their picture and contact information such as facebook, email, phone, twitter, or website form.

We used votesmart's API to look up the data based on your zip code.  We use Redis for caching, nginix for our webserver, and digital ocean
for our hosting.  The backend was all written in Python, while the client was built with Titanium.

I was really pleased with the app performance - Redis was a big help here.  The client was nice looking for a bunch of non-designer
programmers and also performed well. In just 24 hours, we created a snappy cross platform mobile app that really solves a problem 
many people have.

We won btw :)

![Let your voice be heard](/images/lyvbh1.png)
![House of Representatives](/images/lyvbh2.png)
![State Government](/images/lyvbh3.png)
![Local Government](/images/lyvbh4.png)