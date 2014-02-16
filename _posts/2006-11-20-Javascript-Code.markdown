---
layout: post
title: Javascript Code
date: 2006-11-20
---

I've written a few posts about using javascript with web services. Nothing amazingly unique about this code. It's IE6 only.

{% highlight html %}
//this calls "mapfunc()" when the page loads
<body onload="mapfunc();">
{% endhighlight %}
<br>
{% highlight javascript %}
//calls StartProgress then it sends the packet
function mapfunc(){
    StartProgress(40); //displays and increments a progress bar

    //sends the packet, the response is handled by receivemapResponse
    sendPacket("",receivemapResponse);
}


//sends the packet - the packet can be any text. It is blank for the heatmap
function sendPacket(packet,OnReadyStateChangeFuntion){
    webservHTTP=new ActiveXObject("MSXML2.XMLHTTP.3.0");
    webservHTTP.Open("POST", webservurl, true);
    webservHTTP.setRequestHeader("Content-Type","text/xml; charset=utf-8");

    //sets the response funtion - passing functions in javascript is very powerful
    webservHTTP.onreadystatechange = OnReadyStateChangeFuntion;
    webservHTTP.send(packet);
}

//this function is called when a response is received
function receivemapResponse(){
    if (webservHTTP.readyState==4){
        if(webservHTTP.status==200 && webservHTTP.statusText == "OK"){
            //loads the response into the page
            $("heat").innerHTML = (webservHTTP.responseText);
            StopProgress();//stops the progess bar once finished
        }
        else {
            StopProgress(); 
        } 
    }
}

//progress bar functions and html
function $(id){ return document.getElementById(id)};
    var progressID;
    function incrementProgress(){
    var cwidth = $("progress").style.width;
    cwidth = Number(cwidth.substr(0,cwidth.indexOf("p")))+2;

    if(cwidth != 200)
        $("progress").style.width = cwidth + "px";
    else
        $("progress").style.width = "0px";
}
function StartProgress(interval){
    $("progresstext").innerHTML = "Loading.....";
    $("outerprogress").style.display = "";
    progressID = setInterval("incrementProgress()",interval);
}
function StopProgress(){
    clearInterval(progressID);
    $("progresstext").innerHTML = "Loaded!";
    $("progress").style.width = "100%";
    setTimeout("FinishProgress()",500); 
}
function FinishProgress(){
    $("outerprogress").style.display = "none";
    $("progress").style.width = "0px";
}
{% endhighlight %}
<br>
{% highlight html %}
<!--html-->
<span id="outerprogress" 
    style="position:absolute;Right:0px;top:0px;width:200px;
    height:20px;border:black solid 1px;display:none;background-"><!--border-->

<!--progress bar-->
<span id="progress" style="width: 0px;overflow:hidden;height:20px;">

<span id="progresstext" style="font-weight:bold;padding-left:5px;
        height:20px;vertical-align:bottom;"></span><!--static words-->

</span>

</span>
{% endhighlight %}
