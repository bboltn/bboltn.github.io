---
layout: post
title: onmouseover onmouseout overrides hover in IE6
date: 2006-11-21
---

Today I was going to use some css for a simple mouse rollover. I typed..


td.container:hover{
text-decoration:underline;
}

This didn't work because I was already using the onmouseover and onmouseout events for that TD element. To get the same effect I changed the onmouseover call like so...

was...

```
onmouseover="cellover('#EDEDED')
```

now is...

```
onmouseover="cellover(this,'#EDEDED')
```

and I changed the cellover event to use the this keyword

{% highlight javascript %}
function cellover(tablecell, previouscolor){
    //.....
    tablecell.style.textDecoration = "underline";
    //...
}
{% endhighlight %}

and I changed the cellout event to...

{% highlight javascript %}
function cellout(tablecell, previouscolor){
    //.....
    tablecell.style.textDecoration = "";
    //...
}
{% endhighlight %}

simple fix but still annoying.
BTW, the cellover/out functions do a slow transition from the previous color to another color.