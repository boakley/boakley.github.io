---
layout: post
title:  "Introducing robot extension for brackets"
date:   2014-07-20 10:00:00
categories: robot, brackets
---

Looking for a good text editor for creating robot framework plain text
files? I've been working on an extension for the fantstic
[brackets](http://www.brackets.io) editor. To install, simply install the
brackets editor, go to the extension manager, and search for "robot".

**Project page**: <https://github.com/boakley/brackets-robotframework>
**Project wiki**: <https://github.com/boakley/brackets-robotframework/wiki>

# Features of the extension

The robot extension for brackets provides the following features:

* syntax highlighting
* code folding
* smart handling of the tab key
* code completion (if you have [robotframework-hub](
https://github.com/boakley/robotframework-hub/wiki) installed)
* in-editor keyword documentation (again, if you have robotframework-hub installed)

# What is "smart handling of the tab key"?

I recommend using the pipe-delimited plain text format for test
cases. I think this is the best combination of easy-to-read and
easy-to-write. Unlike the tab- and space-separated formats, the
separation of cells is more evident, which I think is important.

One downside of this format is that it's tedious typing `| | `
on most lines. Even worse is a continuation line
which begins with `| | ... | `. 

With this extension, pressing tab on a blank line automatically
inserts pipes, spaces and continuation characters intelligently,
removing some of the tedium with this format.

Want to start a new test case? A single tab on a blank line gives you
the opening `| ` (pipe-space) sequence.

Want to add a new statement to the current test case? Two tabs will
get you the leading `| | ` (pipe-space-pipe-space).

Want to add a new cell at the end of the current statement? If the
cursor is at the last character and you press tab, it will insert ` |` 
to start a new cell. Pressing tab immediately again will remove the
trailing ` | `, start a new line, and then insert the same number of
pipes and spaces as the line you were just editing.

The general idea is to try and get the tab key to "do the right
thing". I'm still refining exactly what that means, but what it has
now seems to work pretty well.

# Why another extension for another editor?

There are already extensions for several popular text editors. Why
create another one?

If I'm honest, it's partly due to my own hubris. I have some slightly
radical ideas for where I want this extension to go, and these ideas
might not mesh with existing projets. So, why not write my own?

Another factor is that brackets is based on the
remarkable [codemirror](http://codemirror.net/) widget, and I had
recently spent a lot of time working with codemirror at my previous
job. I'm wanting to strengthen my own javascript skills (which are
extremely weak), so this is a chance for me to grow, professionally. 

Considering all that, it was easier for me to create a new extension
rather than to fork an existing extension and become a contributor.

# Integration with robotframework-hub

Another project I've been working on is 
[robotframework-hub](https://github.com/boakley/robotframework-hub/wiki). The hub is a web
app and api for serving up information about keywords. 

If you are running the hub on your machine, the brackets extension can
use the hub API to provide autocompilete and in-editor keyword
documentation. Soon you'll also be able to search your keywords right
within the editor. 

# Summary

My goal with this extension is to give automation engineers a high
quality editing tool, so they can focus more on the test case and less
on the mechanics of editing the test.

# Acknowledgements

A huge thank-you to my current employer, [Echo Global
Logistics](<http://www.echo.com>) who generously allows me to work on
this project as part of my day job.





