---
layout: post
title: my latest project and more cool buzz words AJAX
date: 2006-11-17
---

My latest project is tool that prospective clients can use to determine what product they should buy from TSYS.

It looks like a periodic table -- only upside down. It is very strange but supposedly very useful. I don't deal with that stuff so I would not know. It was fun to make though.

All of the data that this tool uses would fit neatly in a relational database. Because of constraints in sharepoint, it can not live in a database. Sharepoint uses something called a list, to store user created data.

So where was I going to store all this data? An idea came to me: you could create several lists in Sharepoint then enforce a relationship between then. With out the help of a DBMS your program needs to maintain this relationship.

This wasn't too hard. Instead of your traditional insert, edit, delete and select statements, I created functions that did this for me. These functions also ensured that foreign key were correct and that I wasn't inserting a string when it should be an int. 

The hard part came when I started running joins against this data. This involved lots of loops and it was very slow (I have learned to respect anyone that creates a true dbms -- it must be very difficult). A general rule in web development is pages shouldn't take longer than 3 seconds to load. Mine took up to 10 seconds to load.

I had read in several articles that web services and javascript, called AJAX, can make a better user experience. This was my reason for using web services. Until now, all my web services used SOAP to send data back and forth. I was always the consumer of the web services and never created any. Since SOAP is a lot of work to parse with javascript, I really didn't want to do that. I quickly found out that you don't need xml/soap/.net at all. [It's just a web page](/2006/11/15/ahhh-web-services.html).

In the end I took those same pages that were slowly creating this heatmap and started calling them with my javascript. Because the web service calls were asynchronous, I could display a progress bar while the page loaded. This distracts users. They forget something is slow when they see a progress bar. It's like dangling keys in front of a baby.

All that's left now is creating a better administrative tool and making it look pretty. :)