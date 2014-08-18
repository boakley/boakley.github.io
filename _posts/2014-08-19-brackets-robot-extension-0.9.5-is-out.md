---
layout: post
title:  "Brackets robot extension 0.9.5 is out"
date:   2014-08-18 08:00:00
categories: general, robot, brackets
---

I've pushed a new version of the robot framework plugin for
brackets. This version has improved coding hinting support. Code hints
now behave a bit more like other editors. 

There is also now some basic support for hinting variables. If you
type "${", a list of all variables in the current file will be
presented. I'll be improving this in future releases to include
variables defined in resource files. 

Another feature is a special shortcut `vv` -- type `vv` at the start
of a cell to automatically insert `${}`, move the cursor inside the
curly braces, and bring up the list of variables. It's a seemingly
simple thing, but seems to add to the editing experience by cutting
down the number of times you have to type cumbersome characters. 

Finally, keyword hints (when you press control-space in a place where
a keyword is likely) now includes local keywords. Prior to this change
it only picked up keywords in external libraries and resource files.



