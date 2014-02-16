---
layout: post
title: How do I grant anonymous access to a url using FormsAuthentication
date: 2009-09-02
---

I originally posted this question on [stackoverflow.com](http://stackoverflow.com/questions/1354185/how-do-i-grant-anonymous-access-to-a-url-using-formsauthentication/1370820#1370820). I've re-written it for this post.

The webapp I was working on required authentication for most tasks. This means, you need to login to do just about anything. There were a few urls, namely the /default.aspx, /scripts, /images, and /styles, that I wanted any user to be able to access.

After reading the FormsAuthentication documentation up and down I came across the location tag.

The location tag can be used to configure a specific url resource. In my case I wanted to configure a few urls and folders specifically.

{% highlight xml %}
<location allowOverride="true">
<system.web>
<authentication mode="Forms">
<forms loginUrl="~/Account/LogOn" timeout="2880" slidingExpiration="true" />
</authentication>
<authorization>
<deny users="?" />
</authorization>
</system.web>
</location>

<location path="default.aspx">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>
{% endhighlight %}

This still didn't work. I hoped this would allow anonymous access to default.aspx but it didn't.

It was a simple enough fix. I didn't have the allow/deny in the correct order. According to MSDN, "the authorization module grants or denies access to a URL resource depending on whether the first access rule found is an allow or a deny rule."

In my case I needed to put all my public stuff first (default.aspx, home,styles, images, scripts) and then I put a deny on everything else. I left out the path on the last location tag. That makes it apply to all files and subfolders.

End result, a user can get to the homepage, pull up images and styles, but for everything else must log in.

Here's my web config file now:


{% highlight xml %}
<!--AUTHORIZATION AND AUTHENTICATION RULES-->
<location path="default.aspx">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>

<location path="Home">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>

<location path="Styles">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>

<location path="Scripts">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>

<location path="images">
<system.web>
<authorization>
<allow users="?"/>
</authorization>
</system.web>
</location>


<location allowOverride="true">
<system.web>
<authentication mode="Forms">
<forms loginUrl="~/Account/LogOn" timeout="2880" slidingExpiration="true" />
</authentication>
<authorization>
<deny users="?" />
</authorization>
</system.web>
</location>

<!--END AUTHORIZATION AND AUTHENTICATION RULES-->
{% endhighlight %}