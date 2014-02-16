---
layout: post
title: Funtional Programming and more
date: 2007-04-01
---

I've been really excited about what functional programming is and what it can do. I never understood it until I started to do a lot of javascript development at work. For the uninitiated, functional programming is when you treat functions like they are variables. Functions are "first class objects." You can assign values to functions, and pass functions to other functions.

### Example

This is what you want to do when your request either fails or succeeds

{% highlight javascript %}
function successfunction(text){ alert("success:" + text);}

function failfunction(text){ alert("fail:" + text);}
    /*This is a combination of anonymous functions and functional programming.
    I create a anonymous function and assign it to makeRequest. 
    This function has two things - an anonymous function who's value is stored 
    in anonTemp and the makeHTTPRequest function who's returned value is 
    stored in httprequest. I'm not showing the code for makeHTTPRequest 
    because I don't remember but trust me that it is assigning anonTemp 
    to a property that will be called when a response comes.*/

    var makeRequest = function (successfunction, failfunction){
    var anonTemp = function(){ receiveResponse(successfunction, failfunction);}
    var httprequest = makeHTTPRequest(anonTemp);
}

//receiveResponse looks at the properties of httprequest 
//  and determines if it succeeded or failed.

function receiveResponse(success,fail){
    //pseudo code httprequest was successful
    success(httprequest.responseText);
    //pseudo code httprequest was a failure :)
    fail(httprequest.response.Text);
}
{% endhighlight %}

OK so this post is just shite, but sometime in the future I will post the full code. Basicially Im trying to make the point that javascript lets you do stuff that would be very hard (C) or kinda hard (C#) very easy. 

Also, I was playing with Ruby a few nights ago and was just amazed that you could do this:

{% highlight bash %}
print 5.tos
=>5
print "5".toint * 8
=>40
{% endhighlight %}

What? numbers and literals have methods???
