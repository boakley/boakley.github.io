---
layout: post
title: Robot extension for brackets 1.0.0
---

After a bit too long of a delay, version 1.0 of the robot framework
extension for brackets is available. Download and install it in the
usual way, through the extension manager.

This version brings two significant new features: keyword search, and
the ability to run tests right from within brackets. Both of these
features are available via hotkey, but can also be started from 
the new Robot menu on the menubar. 

## Keyword search

If you are running the [robot framework
hub](https://github.com/boakley/robotframework-hub/wiki), you can
search through all of the keywords right from within brackets.
From the Robot menu select "Show keyword search window" and it 
will display a list of keywords along with their synopsis. You
can filter the list, and there is a link that allows you to 
paste the highlighted keyword into the editor.

[![image](assets/images/brackets-keyword-search_thumbnail.jpg)](assets/images/brackets-keyword-search.png)

## Test runner

Version 1.0.0 now includes the ability to run robot right from within
the editor. When you run a test, a window will slide up from the
bottom with the output of the pybot/jybot command. 

The command to be run is configurable. If you include the string 
%SUITE in the command, it will be replaced with the name of the 
suite that is currently being edited. For example, if you are
editing "smoke.robot", "%SUITE" will be replaced with "smoke". This 
would typically be used with the --suite option.

[![image](assets/images/brackets-runner_thumbnail.jpg)](assets/images/brackets-runner.png)

## Robot Menu

This version adds a "Robot" menu to the menubar, which provides a way to learn
the shortcuts associated with the test runner and keyword search.

## Bug fixes

In addition to the new features, a few small bugs have been ironed out
as well, such as better support for dark themes.
