---
layout: post
title: Semicolons protect you
date: 2014-01-30
---
I've been wondering why some people put a semicolon at the end of their objects

{% highlight javascript %}
var func = function(){
    console.log("hey3");
}; //semicolon

var func = function(){
    console.log("hey3");
} //no semicolon 
{% endhighlight %}


Both of these above statements define the function 'func' and nothing more.  Lets see what happens when you forget it.

{% highlight javascript %}
var func = function(){
    console.log("hey2");
}
//comments and whitespace here
(true);
{% endhighlight %}

This immediately defines func and then executes it.  Whoops!  Probably didn't mean to do that.  This can happen if you're not careful OR if you are using a tool that combines your javascript code into one file.

{% highlight javascript %}
var func = function(){
    console.log("hey3");
};//semicolon here protects you
(true);
{% endhighlight %}

This creates the function 'func' and the expression (true).

Here's another scenario you might run into.

{% highlight javascript %}
var x = {
    'func':function(){
        console.log("hey5")
    }
}
.func()
{% endhighlight %}

This immediately executes func and now x is undefined.  Did you mean to do this?

{% highlight javascript %}
var x = {
'func':function(){
    console.log("hey5")
    }
};
.func()
{% endhighlight %}

This is a syntax error.  Probably a good thing.

View this [fiddle](http://jsfiddle.net/627YC/2/) for an interactive version of this code.