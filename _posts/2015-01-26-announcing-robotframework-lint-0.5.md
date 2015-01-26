---
layout: post
title: Announcing robotframework-lint 0.5
---

After a bit too long of a delay I've finally published version 0.5 of
robotframework-lint. I'm officially calling this beta software now,
and it's actually quite close to production-ready. All it really needs
is a bit more real-world use.

One of the biggest changes is that rules can be configured. For
example, one new rule checks for lines that are greater than 100
characters. If that threshold doesn't work for you, you can set your
own threshold with the `--configure` option. The `--configure` option
accepts a string of the form _"\<rule name\>:value"_. 

For example, to configure the LineTooLong rule to flag a warning 
if a line exceeds 80 characters instead of the default 100 you
would use it like this:

    $ rflint --configure LineTooLong:80 

Along with this change comes a small handful of new rules, some of which
were contributed by Guy Kisel. Guy also gave some input into the configurable
rule feature. Thanks, Guy!

  - LineTooLong
  - FileTooLong
  - TrailingBlankLines
  - TooManySteps (provided by guykisel)
  - TooManyTestCases (provided by guykisel)

tip: to see the documentation for a rule, use the `--verbose` option
along with the `--list` option (eg: `rflint --list --verbose`). The
formatting is a little wonky, which we'll fix in a later release.

Other than that, there were a few bug fixes, and a new feature added to allow
rule-writers to have access to the raw text in case data you wanted to check
was being thrown away or altered by the parsing process.

## Getting rflint

robotframework-lint is available from pypi, which means you can install it with pip:

    $ pip install --upgrade robotframework-lint

### Use the source, Luke!

robotframework-lint is hosted on github:

<https://github.com/boakley/robotframework-lint>

## I love feedback!

If you are using robotframework-lint, or are considering using it, or have decided
_not_ to use it, I'd love to hear from you. 

## Acknowledgements

A huge thank-you to my current employer, Echo Global Logistics
(<http://www.echo.com>) who generously allows me to work on this
project as part of my day job.

Thank you also to Guy Kisel who has submitted some new rules.
