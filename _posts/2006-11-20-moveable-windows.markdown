---
layout: post
title: moveable windows
date: 2006-11-20
---

There is already plenty of code that you can use to make moveable windows in javascript. This isn't the best and it's only been tested in IE. One problem Im having: When you click the header of a window the window's top left corner snaps to the mouses location. This makes a jerky window.

{% highlight javascript %}
<!--javasscript-->
var mousetimer;
var down = false;

//alot of this code in unnecessary.
// I was trying different things to get rid of the jerkyness
function coordinates(){
    if(down){
        mousex = event.x
        mousey = event.y
        windowx = wrapper.style.posLeft;
        windowy = wrapper.style.posTop;
        newx = mousex;
        newy = mousey;
        wrapper.style.posLeft = newx;
        wrapper.style.posTop = newy; 
    }
}
function startmonitor(){ down = true;}
function stopmonitor(){ down = false;}
function $(id){ return document.getElementById(id); }

{% endhighlight %}

<br>

{% highlight html %}
<!--html-->
<body id="mainbody" onmousemove="coordinates();" onmouseup="stopmonitor();">
<div id="wrapper">
<!--when you click on the border it sets down to true. 
    Now coordinates can start updating wrapper with the new mouse coordinates-->
<span style="border: 1px solid black;width:100%;background-color:blue;" 
onmousedown="startmonitor();" onmouseup="stopmonitor();">
Click here to move me</span><br>

Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
when an unknown printer took a galley of type and scrambled it to make a 
type specimen book. It has survived not only five centuries, but also the 
leap into electronic typesetting, remaining essentially unchanged. It was 
popularised in the 1960s with the release of Letraset sheets containing Lorem 
Ipsum passages, and more recently with desktop publishing software like Aldus 
PageMaker including versions of Lorem Ipsum.

</div>
{% endhighlight %}