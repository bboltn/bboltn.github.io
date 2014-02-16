---
layout: post
title: Website password handling is crap
date: 2011-08-01
---

Over the last few months I've been using very complicated and long passwords (with the help of 1Password).  It turns out that many websites cannot handle complicated passwords.  Some outright complain.  They give you a warning telling you that your password is too long or that you cannot include special characters.  This is annoying - especially when it is a banking website*.  At least nothing breaks, and you have a guide as to how to create your password.  Some sites don't allow special characters.  1Password is nice because it will allow you to create a complicated password without special characters. Usually this ends up just being a really long word - 20 characters or more.

Other sites are more insidious.  They break in weird and harmful ways.  A few things will happen:

You will get a nasty error - an unhandled exception.  At this point, you may or may not have changed your password.  YMMV, but I have found that the password is usually changed but something exploded during the transit.  In the end you are alright, but it is dang frightening.

You will change your password, but it doesn't really change.  When you go back to log in, you cannot get in.  This one is the worst.  At this point you have to reset your password which usually involved guessing the answers to some security questions**.  Answers you cannot ever seem to get right.

*banking websites have terrible password policies.  One of my banks has an 8 character limit with no special characters.

**security questions are not secure.  In the age of facebook, many people know my mother's name or the high school I went to.  Please stop using these in sites!  In the meantime, just make up answers and write them down in 1Password.  Better yet, make complicated passwords as your answers.  Some sites don't require security questions, but they do recommend it.  Screw that recommendation.  Just don't fill in the data.

....

Oh yeah, I had another run in with a printer today.  I swear these things are out to get me.