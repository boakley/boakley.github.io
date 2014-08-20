---
layout: post
title:  "Why I like pipe-formatted tests"
date:   2014-08-20 12:00:00
categories: robotframework
---

Robot framework supports several different formats for its test
cases. You can write tests in 
[HTML](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#html-format), 
[reStructuredText](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#restructuredtext-format), 
[tab-separated values](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#tsv-format)
(eg: export from a spreadsheat program), and 
[plain text](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#plain-text-format) 
with either pipe-separated fields or space-separated fields.

Each format has advantages and disadvantages, mostly centered around
how easy it is to write the tests vs how easy it is to read the test
after it has been created. These two goals are sometimes in conflict
with each other. 

This article gives a very brief rundown of the advantages of each, and
covers why I eventually came to embrace the pipe-separated plain text
format as the best of the available formats.

## HTML

HTML is my least favorite format for test cases. This is due to two
reasons: it can be difficult to write the tests, and it can be
difficult comparing two versions of a test. 

The tests are difficult to write because HTML editors aren't optimized
for writing robot, so you're trying to write test cases in a tool
designed to create websites. The tool has a different goal than the
user. Of course, you can use a plain text editor, but then you're
cursed with having to hand-edit HTML tags (though, smart editors can
help ease that pain). 

Because your test case data is wrapped in HTML tags, it can make the
test cases hard to diff and merge simply because of all of the extra
markup. Worse, in my experience, different web editors may introduce
differences in the markup by adding or removing whitespace or
linebreaks. If the people in an organization use different tools, it
can cause problems for comparing versions of a test case -- a single
line change to a test case in a different tool may end up reformatting
the whole file. 


## reStructuredText

Using reStructuredText has an advantage similar to HTML in that you
can create test documents that are very easy to read. Writing
reStructured text is at least arguably easier to write than HTML since
the markup doesn't rely so much on tags as it does simple conventions, so
you get the best of both words -- fairly easy to write, and definitely
easy to read.

What I don't like about reStructuredText is that it's still a bit
verbose. While you can "draw" test tables that indeed look like
tables, you _have_ to draw test tables that look like tables. Since
the focus of writing tests should be on the logic and data of the
test, having to spend extra effort to make the tables look like tables
is onerous.

There's another option where you can use code blocks. Within a code
block you can use the space-separated format. However, if you're going to use
the space-separated format, why add the extra complexity of
reStructuredText on top of it?

I would be interested in hearing from someone that is successfully
using reStructuredText for their tests. Maybe I can be convinced it's
the way to go.


## Tab-separated values

My first exposure to robot was at a company where we settled on the
tab-separated format. This is arguably the easiest to type when  using
a standard text editor, since it's just a single keypress to start a
new cell. The problem with tab-separated files, in my opinion, is the
fact that it's hard to distinguish between a tab and just a bunch of
spaces. And, depending on your tab stops, a single tab may often look
like a single space, leading to ambiguity.

You also have the same (dis?)advantage as using tabs in software --
different people have different settings for tab stops. Some see this
as an advantage, but often results in code that lines up and reads
properly to one person but not another. 


## Plain text, space-separated format

The plain text, space-separated format seems to be the most
popular. This is the format that the robot framework inventor uses,
and many examples I see on the internet use this format. It has the
advantage that test cases can read very much like English language,
which definitely is one of the main appeals of using a keyword driven
testing language.

The Achilles heal of this format, in my opinion, is that it leads to
ambiguity. Two spaces can separate two cells in a row, but in print
and on websites it's can be difficult to visually distinguish one
space from two. To work around that, the robot framework user guide
suggest using four spaces, but then you lose some of the
readability, plus it's just a pain to type four spaces between each
cell. 


## Plain text pipe-separated format

This is the format I prefer, because I think it strikes a nice balance
between being easy to read and write. It has many of the same
advantages as the space- and tab-separated formats, but it has one
distinct advantage in that it is much less ambiguous. There's no
denying the presense of a pipe between two fields. 

The downside to the pipe separated format is that pressing
space-pipe-space is tedious, and also difficult to say out loud when
teaching others. Another downside is that the presense of a pipe
removes some of the "english-like" features of the space separated
performance. 

In fact, having to type a pipe is a pretty big downside. Just as I
would not want to type four spaces between two cells, typing
space-pipe-space is also somewhat annoying. Not only that, but 
on many non-US keyboards, the pipe character is
particularly hard to type. If I had one of those keyboard I would
definitely gravitate toward the space-separated format.

That, to me, is just about the only real downside to using the
pipe-separated format. In fact, I liked the format enough, and hated
typing the pipe enough, that I wrote my own editing tools to eliminate
the pain. 

A few years ago I wrote a desktop app that let you type a pipe simply
by pressing the tab key. You then get the ease of editing that you
would get with the tab-separated-value format, but with the clarity of
the pipe-separated format.

This proved to be a fantastic solution. However, I was spending a lot
of my time writing a basic text editor around this single feature,
rather than focusing on adding even more features.

That's when I switched to writing a [robot extension for
brackets](http://localhost:4000/2014/07/20/introducing-robot-extension-for-brackets/). My
extension has a couple of key features that I believe gives the
best editing experience for robot framework tests. You have the ease
of entering separators by pressing tab, the clarity that comes with
pipes rather than spaces, yet the ease of reading because the pipes
are rendered in a dim color, making them less dominant. And, because
it is an extension to an existing editor, I can focus on adding
additional features such as in-line keyword documentation, code hints,
and so on.

## Summary

I prefer the pipe-separated plain text format, and use that at work,
and in my blog posts and answers on stackoverflow. It's what I
recommend to anyone just getting started. But honestly, all of the
supported formats are great and have their place. I think that the
fact they are all plain text gives robot a lot of its appeal, because
the tests play very well with development tools we already use -- text
editors, source code control, diff, etc.






