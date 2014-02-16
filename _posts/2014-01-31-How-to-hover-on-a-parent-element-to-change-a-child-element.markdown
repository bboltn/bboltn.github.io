---
layout: post
title: How to hover on a parent element to change a child element
date: 2014-01-31
---
I was curious about how to show a child when hovering over a parent element.  Turned out to be pretty easy.

{% highlight html %}
<div class="parent">
    Parent
    <div class="child">Child</div>
</div> 
{% endhighlight %}

Child is hidden by default
{% highlight css %}
.child {
    visibility: hidden;
}
{% endhighlight %}

On hover the child is visible
{% highlight css %}
.parent:hover .child {
    visibility: visible;
}
{% endhighlight %}

[View Fiddle Here](http://jsfiddle.net/brianbolton/vFp3K/)