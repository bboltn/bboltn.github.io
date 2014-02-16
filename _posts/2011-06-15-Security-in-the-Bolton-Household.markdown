---
layout: post
title: Security in the Bolton Household
date: 2011-06-15
---

### What happened....

My wife got a nasty virus on her netbook several weeks ago.  Someone uploaded an infected PDF to an education website.  My wife (she's a teacher) downloaded this PDF.  With no interaction from her, besides opening it, it immediately installed a fake antivirus program.  It then said it found a virus and asked for her credit card to upgrade so that the program could remove the virus.  Adobe was set to automatically update, but I guess it either had not fixed this vulnerability or we had not updated yet.

She was smart enough to realize this was a scam and immediately got me to help out.  I didn't have time to work on it right then.  I shut the machine down and removed the battery.  Days later I decided to reformat and re-install windows.

To compound all this, PSN was hacked a few weeks earlier.  I used that same user name and password on many websites - including some banking websites.

OK, so I was pissed and feeling very vulnerable.  And now I was motivated to fix my shit.

### This is what I WASN'T doing

- Use long complex passwords
- Use unique passwords for each website/login
- Run as a least privileged user
- Turn on firewalls
- Turn on antivirus
- Use something besides Adobe for PDFs

### Now things are a little different.

I use 1Password + Dropbox to create and manage all of my accounts (all 128 of them).  Each one has a unique password.  Each one is complex - as complex as the system would allow.  Some sites enforce bad password policies.  I use Dropbox to sync all my passwords across all devices.  That's a Window XP machine, Window 7 machine, iPhone, and Macbook Pro.

All computers have at least 2 accounts - 1 user and 1 admin.  

I had firewalls turned on in Windows, but not OS X.  I've turned that on now.  

I'm using Foxit Reader for PDFs on Windows.  I use the built in PDF reader for OS X and iOS.

And finally, I've done the unthinkable.  I vowed to never install antivirus.  I always considered it a resource hog.  On the recommendation of my security pro friend, I purchased Norton 360 and installed it on all of my Window machines.  They sell a copy for OS X but I'm going to hold off on that purchase until Lion comes out.

### How's this working out for me? 

I've been using this setup for 2 maybe 3 weeks now.  The password thing freaked me out at first.  I honestly don't know any of my passwords.  I just have my 1 master password and that's it.  In practice, it works out fine.  I just copy/paste those passwords into forms no problem.  Even works well on iPhone.  One caveat here is typing these passwords into a machine like a PS3 or Apple TV.  That's a PITA for sure.  But it's a one time thing that I'll never have to do again.

Running as a least privileged account works fine in Windows 7 and OS X.  It's not workable in Windows XP.  Too many programs require admin rights to do basic tasks.  Programs would lock up or just error out.  I ended up going back to using admin accounts in XP.

The firewall is not that great on OS X.  It doesn't seem to trust iTunes even though I've added it as a trusted program.  Oh well, I don't mind clicking Allow for when iTunes downloads content.

I've had no problems with Foxit Reader or my Norton 360.

All in all, I'm happy with my current setup.