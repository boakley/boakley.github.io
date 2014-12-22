---
layout: post
title: Announcing robotframework-lint 0.4
---

I just pushed version 0.4 of robotframework-lint to pypi. While we're not quite
at a 1.0 release just yet, this release is a major step forward. Following is a 
brief summary of the major new features:

## rflint command

Prior to this version, to run rflint you needed to call it like this:

    $ python -m rflint <options> <files...>

Starting with this version, a "rflint" command is installed along with the
rflint module. On windows this will be a .exe, on other platforms it's a script.


## Directory processing

If you give rflint a path to a directory, it will process all of the files in 
that directory that end with ".robot", ".txt" or ".tsv". If you supply the
--recursive option, it will also recurse into every child directory.


## Argument files

You now have the ability to create a file that defines the severity level for
all rules. This has the same syntax as robot framework argument files, and even
the same option name.

For example, if you always want to ignore RequireSuiteDocumentation, and you
want an error for RequireKeywordDocumentation, you can create a file that looks
like this:

    # rflint.args
    --ignore RequireSuiteDocumentation
    --error RequireKeywordDocumentation

If you name your file 'rflint.args' you can use it like so:

    rflint --argumentfile rflint.args file1.robot file2.robot ...


## Other improvements

In addition the above major features, there have been several other enhancements,
such as only printing filenames for files that actually have warnings and
errors. Rflint now treats unicode non-breaking spaces correctly, and if you 
give unknown files on the command line rflint will write warnings to stdout. Finally, 
the list option (--list/-l) can be combined with the verbose option (--verbose/-v)
to display both rule names and their documentation.


## Getting rflint

robotframework-lint is available from pypi, which means you can install it with pip:

    $ pip install --upgrade robotframework-lint

## Use the source, Luke!

robotframework-lint is hosted on github:

<https://github.com/boakley/robotframework-lint>

## Acknowledgements

A huge thank-you to my current employer, Echo Global Logistics
(<http://www.echo.com>) who generously allows me to work on this
project as part of my day job.

Thank you also to Guy Kisel who has submitted a few issues and patches.
