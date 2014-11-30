---
layout: post
title:  "robotframework-lint preview"
date:   2014-11-30 19:27:00
categories: general, robot
---

I'd like to introduce a preview release of a new tool I'm developing
called robotframework-lint.  

Robotframework-lint, or rflint for short, is a lint-like static
analysis tool for robot framework plain text files. For a given test
suite or resource file it will run a series of rules against the
suite, its test cases and keywords. 

The purpose is to automatically detect certain anti-patterns in your
test assets. For example, it can catch duplicate test case or keyword
names, flag deviances from local standards such as disallowing spaces
in tag names. 

# A brief example

Consider the following test suite file:

    *** Test Cases ***
    | Hello, rflint!
    | | [Tags] | example tag
    | | log | hello, rflint!

This is what happens when you run rflint against this file:

    $ python -m rflint hello.robot 
    + hello.robot
    W: 1, 0: No suite documentation (RequireSuiteDocumentation)
    E: 3, 0: No testcase documentation (RequireTestDocumentation)

Rflint caught two problems:

  * A warning that there is missing suite documentation
  * An error that there is missing test case documentation
