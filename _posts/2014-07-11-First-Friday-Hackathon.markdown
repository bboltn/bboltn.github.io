---
layout: post
title: "First" Friday Hackathon - July 11, 2014
date: 2014-07-11
---

With the July 4th weekend the hackathon was moved to the second friday of the month.

My project for this event was to create an animated gif from a video.  I started using
OpenCV, but its just more complicated and four hours (minus an hour for talking and eating)
isn't enough time to get really deep into a technology.  I changed to using ffmpeg and imagemagick based on work
done by another member of the group several hackathons ago.

{% highlight bash %}
ffmpeg -ss 0 -i $1 -t 5 -s 640x480 -f image2 %03d.png
convert -delay 20 -loop 0 *png $1.gif
rm *.png
open -a "Google Chrome" $1.gif
{% endhighlight %}
