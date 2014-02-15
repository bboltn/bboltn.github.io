---
layout: post
title: onmouseover onmouseout overrides hover in IE6
date: 2006-11-21
---

Today I was going to use some css for a simple mouse rollover.  I typed..<br /><br /><blockquote>td.container:hover{<br />text-decoration:underline;<br />}</blockquote><br />This didn't work because I was already using the onmouseover and onmouseout events for that TD element.  To get the same effect I changed the onmouseover call like so...<br /><br />was...<br /><blockquote>onmouseover="cellover('#EDEDED')</blockquote>now is...<br /><blockquote>onmouseover="cellover(this,'#EDEDED')</blockquote><br /><br />and I changed the cellover event to use the <span style="color: rgb(51, 51, 255);">this</span> keyword<br /><blockquote>function cellover(tablecell, previouscolor){<br />//.....<br />tablecell.style.textDecoration = "underline";<br />//...<br />}</blockquote><br /><br />and I changed the cellout event to...<br /><blockquote>function cellout(tablecell, previouscolor){<br />//.....<br />tablecell.style.textDecoration = "";<br />//...<br />}</blockquote><br />simple fix but still annoying.<br />BTW, the cellover/out functions do a slow transition from the previous color to another color.
