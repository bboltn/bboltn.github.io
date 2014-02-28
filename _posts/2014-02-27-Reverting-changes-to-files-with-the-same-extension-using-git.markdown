---
layout: post
title: Reverting changes to files with the same extension using Git
date: 2014-02-27
---

A program I was using edited about 100 files and I didn't want to commit these files.  Here's a simple script I used to reset these files back to their original state.

```
git checkout -- `git status | grep -E '.js' | awk '{print $3}'`
```
