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
    E: 2, 0: space not allowed in tag name: 'example tag' (TagWithSpaces)
    E: 3, 0: No testcase documentation (RequireTestDocumentation)

Rflint caught three problems:

  * A warning that there is missing suite documentation on line 1
  * An error saying that there is a tag with a space on line 2
  * An error that there is missing test case documentation on line 3

If you want to ignore the TagWithSpaces error you can control that
from the command line:

    $ python -m rflint --ignore TagWithSpaces 
    W: 1, 0: No suite documentation (RequireSuiteDocumentation)
    E: 3, 0: No testcase documentation (RequireTestDocumentation)

# Interactive help

You can get a list of all of the command line options by using the
--help option:

    $ python -m rflint --help
    python -m rflint --help
    usage: python -m rflint [-h] [--error <RuleName>] [--ignore <RuleName>] [--warn <RuleName>] [--list]
                            [--no-filenames] [--format FORMAT]
                            ...

    A style checker for robot framework plain text files
    ...

You can get a list of all of the currently installed rules with the
--list option:

    $ python -m rflint --lilst
    'E DuplicateKeywordNames'
    'E DuplicateTestNames'
    'E RequireKeywordDocumentation'
    'W RequireSuiteDocumentation'
    'E RequireTestDocumentation'
    'E TagWithSpaces'


# Where can I find it?

rflint is available on github: https://github.com/boakley/robotframework-lint

You can also install with pip, which will install the module "rflint"
in the standard place:

    $ pip install robotframework-lint

# Want to contribute?

Would you like to contribute? I would love to have help growing rflint
into an indespensible part of the robot framework toolchain. There is 
an opportunity to work on the base code, or to contribute
rules. Simply fork the repository and submit pull requests. You can
also ask questions on the robotframework-users mailing list. 

# Acknowledgements

A huge thank-you to my current employer, Echo Global Logistics
([http://www.echo.com]) who generously allows me to work on this
project as part of my day job.





