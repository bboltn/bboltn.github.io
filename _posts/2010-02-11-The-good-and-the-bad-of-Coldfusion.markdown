---
layout: post
title: The good and the bad of Coldfusion
date: 2010-02-11
---

Coldfusion (the programming language) is at times very good. It's full of one liners.

Want to get the contents of a google search for monkeys?

{% highlight xml %}
<cfhttp url="http://www.google.com/search?q=monkeys">
{% endhighlight %}

Want to make an FTP connection?

{% highlight xml %}
<cfftp action="open" username="anonymous" connection="Myquery" 
    password="youremail@email.com" server="ftp.website.com" 
    stoponerror="Yes">
{% endhighlight %}

Query a database?
{% highlight xml %}
<cfquery name="qryName" datasource="whatever">
    select * from table
</cfquery>
{% endhighlight %}

What to have locally scoped variables?

ehhhhh can't do it. Yeah, this is the bad part.

Coldfusion doesn't scope its variables by default. So this means that any variable in a function is a global variable. This was a horrible language design decision. I'm sure they have a good reason for it, but it has been kicking us in the butt lately.

For instance, on a website I work on, Person A is getting content they didn't request because Person B requested it after Person A. This is happening because coldfusion isn't scoping Person A's variables correctly. They are getting overwritten by Person B's data. Thus Person A gets Person Bs data.

How did we fix it? Well, we created a structure called LOCALS and all of our local function variables are members of this structure. See that var in front of LOCALS? It is how you force Coldfusion to make a variable local. Why don't we just put var in front of all the variables? Coldfusion demands that all var's be declared at the beginning of the function. Go figure. The code looks like this:

{% highlight xml %}
<cfset locals="structnew()"></cfset>
<cfset locals.x="123"></cfset>
<cfset locals.y="456"></cfset>
{% endhighlight %}

Don't think for a minute I came up with this great idea. I first saw it on Ben Nadel's blog.

It is annoying and tedious and just frustrating. After years of C# and other programming languages, I just took scoping for granted. It's an error that doesn't happen when one programmer tests. You need hundreds or more users running a site to really see this error happen often.

<hr>
In other news, I'm working on a portfolio site for a local artist. I will post site designs in the near future.