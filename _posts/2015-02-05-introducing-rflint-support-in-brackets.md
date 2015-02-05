---
layout: post
title: Introducing robotframework-lint support in brackets
---

I'm happy to announce that the robot framework extension to brackets now
includes integration with robotframework-lint. 

[![image]({{ site.url }}/assets/images/brackets-rflint-integration-1_thumbnail.jpg)]({{ site.url }}/assets/images/brackets-rflint-integration-1.png)  
(click image to enlarge)

The robot extension for brackets now has a very robust set of features:

* syntax highlighting
* code folding
* smart tab key for inserting pipes
* run tests from within the editor
* quickly select contents of a single cell
* autocomplete and inline documentation via robotframework-hub
* search for keywords
* lint support via robotframework-lint

Of course, many of the advanced features of brackets are also
available when editing robot files, including:

* multiple cursors
* split screens
* search and replace across files
* customizable themes

## Using the linting feature

The use of robotframework-lint is hooked into the standard linting
mechanism of brackets, so you can control whether the window of items
will appear or not. In all cases, one or more violations will cause a
yellow triangle to appear on the status line.

To use the linting feature you simply need to define how to run
robotframework-lint. Do this by selecting "Robot Settings..." from the
"Robot" menu, which will display a dialog allowing you define how to
call rflint. 

You can include any rflint arguments that you want. The current file
being edited will be added at the end of the command. The easiest way
to do this is to put all of your options in a file, and reference that
file with the -A/--argumentfile option.

For example, if you have an argument file named
/Users/bryan/rflint.args, you can change the settings to be `rflint -A
/Users/bryan/rflint.args` (note: you cannot use ~ to represent your
home directory; you need to use an absolute filename)

Once it has been configured, robotframework-lint will be called every
time you save a .robot file. If rule violations are detected they will appear
at the bottom of the window. Clicking on an item will move the cursor
at or near where the violation was detected.

## More information on robotframework-lint

For more information about robotframework-lint see
[robotframework-lint wiki](<https://github.com/boakley/robotframework-lint/wiki>)

## Acknowledgements

A huge thank-you to my current employer, [Echo Global
Logistics](<http://www.echo.com>) who generously allows me to work on
this project as part of my day job.




