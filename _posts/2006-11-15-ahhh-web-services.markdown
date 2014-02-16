---
layout: post
title: ahhh web services
date: 2006-11-15
---
I finally realized what the hype was about.

I am working on an internal web site for work and it is SLOW. I have to do pull back lots of data. Mind you this data isn't in a database so there isn't a quick way to get it. So, I (more by accident than purpose) have started offshoring my work with web services.

I am not talking about SOA stuff here, just one-off-project specific web services. Since I hate buzz words I really don't like "web services." Buzz words have a tendency to scare off the uninitiated (like myself) and can lead to confusion and misuse. I think this is why I started using them by accident.

Here is the gist of web services. It's a web page. Yup. That's all it is. A web page. So go out and create a web page. Now you have a web service. Any application that can make http requests can now request your page. And then your page sends it the data. But instead of the data going to a web browser it goes to your application. Then your app can parse the data sent to it anyway it wants. Heck, the data can be anything, binary, text, bananas.

*I feel cheated and kinda mislead. All this hype of web services made me think it was something amazingly hard and it involved .net with xml blah blah... nope it isn't any of that.*

*I will explain in more depth later what I used web services to do and why it was an accident.*

actually, it can't be bananas.