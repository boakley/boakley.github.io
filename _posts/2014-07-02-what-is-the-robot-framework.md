---
layout: post
title:  "What is the Robot Framework?"
date:   2014-07-02 17:00:00
categories: general, robot
---

In my current job we're using [robot
framework](http://www.robotframework.org) as our test automation
framework. My team is tasked with teaching others how to use it,
and to build additional tools to make the process of test automation
easier. I'm going to be writing a lot on the blog about this
framework, so I thought I would give a very brief introduction and
explain why robot is so compelling. 

Robot framework is a generic keyword-driven testing
framework specifically targeted at acceptance test driven
development. Tests are plain text files using a simple tabular
syntax. Because the test cases are plain text, you are free to use 
whatever tools you're most comfortable with (Eclipse, Visual Studio,
emacs, vim, Notepad++, etc).

Robot framework is written in python, is robust and mature, and under
active development. There are several extensions you can use in your
test cases (eg: selenium, database, etc), and there are robot-specific
extensions for other popular tools (eg: jenkins, sublime text,
brackets, etc). 

# What do the tests look like?

There is no canonical example of a robot framework test. It supports
multiple formats, including HTML, reStructuredText, plain text, and
tab-separated data. Personally I prefer the plain text, pipe-delimited
format. It's very diff-and-merge friendly, easy to write and easy to
read. Unlike with tab- and space-separated plain text, the division
between cells in a test case are clearly visible.

Here's an example from the robotframework.org web site, reformatted to
the pipe-delimited format:

{% highlight RobotFramework %}
*** Settings ***
| Documentation 
| ... | A test suite with a single test for valid login.
| ... |
| ... | This test has a workflow that is created using keywords in
| ... | the imported resource file.
| 
| Resource | resource.txt

*** Test Cases ***
| Valid Login
| | Open Browser To Login Page
| | Input Username | demo
| | Input Password | mode
| | Submit Credentials
| | Welcome Page Should Be Open
| | [Teardown] | Close Browser
{% endhighlight %}


Under the "*** Test Cases ***" heading, each line that begins with a
single pipe denotes the name of a test case. Lines that begin with
pipe-space-pipe-space are statements. Typically the first word will
be a keyword (either a built-in keyword or a custom keyword), and 
remainging cells are keyword arguments.

That's about all there is to it -- very straight-forward, easy to read
and easy to write.

# What can the framework be used for?

The robot framework isn't just for testing python code. It can be used
for a variety of testing tasks, including:

* RESTful API testing
* SOAP service testing
* Website testing
* Database testing
* Desktop application testing
* Mobile application testing (with selenium and 3rd party drivers)
* Unit and integration testing (though, there are often better tools 
  for that job)
* Manual testing - scenarios can be written as if they were automated,
  they can prompt the user rather than perform a task.

As you can see, it can be useful for a wide variety of testing
tasks. Now, it might not always be the best solution for any one of
those areas but it's one of the few tools that can be used for just
about all testing tasks. This means you have a single test syntax to
learn, a single reporting structure, a single way to tag and manage
tests, and so on. 

# Other things I like about the framework:

* Robot framework is written in python, and libraries can be written
  in python. Anything you can do with python, you can do in a test
  case. This makes it very easy to extend to do a variety of tasks.
* Robot framework has a remote library interface, which means you can write keywords
  in any language that can open a socket (.NET, java, C, etc). 
* Robot test suites are plain utf-8 text. This means they play nicely
  with source control, making it easy to diff and merge
* You have the choice of writing tests in a BDD (given/when/then)
  style, a procedural style, or in a data driven style. Work the way
  you want, rather than be forced into a particular style of test.
* it has a powerful tagging mechanism
* it has a powerful system for streaming test results to other tools
  and dashboards (called "listeners" if you want to look it up in the
  user guide).


# Summary

Robot framework is a really good testing framework, if your goals are
to use a single framework for a variety of testing and if you want to
use a keyword driven approach. The fact that it's easily extensible
with python and that it plays well with tools you probably already use makes
it a very pragmatic choice for a large variety of testing tasks.

The robot framework project has fairly comprehensive documentation. To
get started, visit <http://www.robotframework.org>.
