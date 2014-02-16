---
layout: post
title: How to change variables in XSLT and Sharepoint
date: 2010-10-27
---

In XSLT you cannot change the value of a xsl:variable once it has been set.

{% highlight xml %}
﻿<xsl:variable name="counter" select="'1'"/>
﻿<xsl:variable name="counter" select="'2'"/> <!-- does not work -->
{% endhighlight %}

This is less than desirable in many many scenarios.  Incrementing a counter in a loop is the first place I needed it.

I wish you could avoid XSLT altogether but not so.  Any developer programming in Sharepoint will eventually have to use XSLT for one thing or another.  Lucky for you, there is a way to get around "write-once" variables in XSLT when used in Sharepoint.

Sharepoint comes with a custom namespace called DDWRT.  Import this namespace into an XSLT file and you will have access to all of its functions.  DDWRT has many functions.  [Check out the reference on MSDN for everything it can do.](http://msdn.microsoft.com/en-us/library/dd583143(office.11\).aspx)

## The Setup

Add the ddwrt namespace to the xsl:stylesheet tag in the XSLT file.

```
﻿xmlns:ddwrt="http://schemas.microsoft.com/WebParts/v2/DataView/runtime"
```

There might be other xmlns statements in the tag.  Just add it last.

## Set the Value


If you want to set the value of a variable, use this function:

```
ddwrt:SetVar('hasquery')
```

You cannot just call SetVar anywhere in your code.  It needs to be inside XML.  I will use ﻿xsl:value-of tag to wrap any set I make.  It will look like this:

{% highlight xml %}
<xsl:value-of select="ddwrt:SetVar('counter','1')" />
{% endhighlight %}
&nbsp;
## Get the Value

If you want to get the value of a variable, use this function:

﻿ddwrt:GetVar('counter')

GetVar always returns a string. So if you are doing a counter like I was, you'll need to cast it to a number after you get the value.  Use the number function built into XSLT to do the conversion.  I use this one line to increment and then set the counter variable:

{% highlight xml %}
﻿<xsl:value-of select="ddwrt:SetVar('counter',number(ddwrt:GetVar('counter')) + 1)" />
{% endhighlight %}
