---
layout: post
title:  "Introducing Robot Framework Hub (rfhub)"
date:   2014-07-18 17:00:00
categories: robot, rfhub
---

I've been working on a new project lately, called Robot Framework
Hub. It's a lame name, I know. Suggest a better name and maybe I'll
use it! 

The project is now to the point where it's ready to be used by more
people than just me and my team. In invite you to take a look. If
you're impatient and want to see some screenshots before going to the
trouble of installing it, visit the rfhub wiki here: 
<https://github.com/boakley/robotframework-hub/wiki>

# What is robot framework hub?

What is the hub (I'll use "rfhub" from here on out)? In short, rfhub
is a light weight, zero configuration web application and api for
serving up documentation for all of the robot framework keywords on
your system.

Tired of hitting the internet for library documentation? rfhub solves
that problem. Also, you can get documentation for all of the keywords
in your local resource files and private libraries in addition to
documentation for built-in keywords and installed libraries. Rfhub
also allows you search across all your keywords at once.

Want to try it out? it's crazy easy to get started. All you need is
python and the robot framework, and a working internet
connection. Open up a terminal or command prompt and issue these two commands:

    $ pip install robotframework-hub
    $ python -m rfhub

That's it! Now you can browse to <http://localhost:7070/doc> to see the
documentation for the keywords on your system. Want to use the api?
<http://localhost:7070/api/keywords> will return all of the keywords as
a JSON object. You can also search by name, or get a list of keywords
for a particularly library. 

If you want to tell it where to find your own keywords, just add one
or more directories as arguments. For example, if you have keywords in
/src/tests/keywords, you can run the hub like this to see the
documentation for all of the resource files in that directory:

    $ python -m rfhub /src/tests/keywords

Although serving documentation is all it does now, 
I have pretty big plans for the hub -- I want it to have a
dashboard to control your testing activities, a way to view robot
framework documentation, and a UI for running tests and viewing test
results amoung other ideas. 

# What rfhub is not

There's another robot framework documentation system out there called
rfdocs (<http://www.rfdocs.org>). rfhub is _not_ a replacement for
rfhub. It _is_, however, an alternative. Whereas rfdocs is an
enterprise-class tool for managing the documentation for multiple
versions of libraries, rfdoc is a tool specifically for viewing the
documentation actually installed on your workstation. 


# Where can I find it?

rfhub is available on github:
<https://github.com/boakley/robotframework-hub>

There's a bit of information on that landing page, along with links to
the source. Be sure to check out the wiki which you can get to from
that landing page. 

# Want to contribute?

Would you like to contribute? I would love to have help growing rfhub
into an indespensible part of your testing toolkit. rfhub is written
in python and uses the flask web application framework. For the front
end I use bootstrap. 

Send me an email and we can work out the details.

# Acknowledgements

A huge thank-you to my current employer, Echo Global Logistics 
(<http://www.echo.com>) who generously allow me to work on this
project as part of my day job.
