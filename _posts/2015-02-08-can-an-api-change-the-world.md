---
layout: post
title: Can an API change the world?
categories: xapi, robot

---

Well, there went my weekend. 

Recently I stumbled on the [Tin Can
API](http://tincanapi.com/) (a.k.a. xAPI, a.k.a. Experience API), and
decided to devote my Saturday to playing around with it. This post is
more about the API than it is about testing, but I promise there's a
test automation component to this story.

## Getting it. Or not.

When I first started reading through the first pages of documentation
I thought "ok, e-learning. Tin Can API is a RESTful interface for
that. Cool. I get it.". If you're a developer, you might be thinking
along the same lines. It's easy to imagine how one might put a RESTful
API in front of an e-learning system.

Only, I didn't _really_ get it, and at this moment you probably don't, either.
It is _so_ much more than just a RESTful interface to an e-learning
system. 

The tin can API is a new standard, meant to be the successor to
[SCORM](http://www.scorm.com). I had never heard of SCORM before, so
that didn't mean a whole lot to me. Fortunately, scorm.com provides a
free non-commercial trial of
[ScormCloud](http://scorm.com/scorm-solved/scorm-cloud-features/) that
includes support for the tin can API, so it looks like it should be
easy to write some simple experiments. I love free trials of web
services. 

## The webinar black hole

I created a ScormCloud account, and then started reading some of the
API docs and drilling deeper into the Tin Can API home page. As I was
poking around I came across a podcast titled [The Impacts of the
Tin Can API: How 8 Companies are Using the Tin Can API
(xAPI)](http://youtu.be/jSQwo1C4feA). Not big on marketing webinars
but curious about how the tin can API is being used, I clicked play. 

Big mistake. That video threw a real monkey wrench into my hacking plans. I
was so blown away by the stories, all I could do was let my mind
wander and wonder about all of the possibilities. There were more
videos [on the same
page](http://tincanapi.com/wp-content/assets/webinar/webinar.html),
and the next thing I know, several hours had gone by. I was stoked.

## Working code, in the time it takes to bake a pizza

I was also hungry. It was lunchtime. I'm a programmer, so... pizza! I
popped a frozen pizza in the oven, came back to my desk, and
figuratively rolled up my sleeves. I really didn't want the day to
pass without writing some code, even though the videos were really
fascinating.

Since my current gig has me writing software for automated testing, I
figured I could start there. We use a tool called [Robot
framework](http://www.robotframework.org) which has a feature where I
can supply python functions that it will call each time a test suite
or test case finishes. Since there's a python client library for the
API, perhaps I can save test results to my StormCloud account. 

Literally in the time it took my pizza to cook (18 minutes) I had
working code that would take a test case or test suite result and
stream messages ("statements" in xAPI terminology) to my StormCloud
LRS (Learning Record Store) as the test was running. 18 minutes from
never having written a single line of tin can API code to having a
working solution. That rocks.

## Can I use it in the real world?

Now, why would I want to save test results to a LRS? I don't know, I
probably _don't_ want to use an LRS to _just_ monitor test results.
However, I can think of two related use cases right off the top of my
head that are intriguing.

I work for a public company, and when new code is published to our
production systems we have some compliance hoops we need to jump
through to prove our software was properly tested. Imagine if our
deployment process including using the tin can API to record which
parts of the application were tested, when, and by whom, during the
final deployment? That might be very useful, and I'm guessing it would
be relatively easy to implement.

Another area where it might be useful is in the on-boarding and
training of our automated test engineers. We have a lot of self-guided
exercises and wiki pages, but we rely mostly on the honor system as to
whether someone worked through the exercises or not. Imagine capturing
which wiki pages they read and which exercises they ran, and compare
that to which (if any) tests they were able to run?  This would allow
us to track their performance, and to fine tune our training
strategies based on which exercises yielded the most positive
results. This could help both the trainer and trainee. 

## Getting usage information

Finally, I'm thinking maybe I could bake this into my [robot framework
extension](https://github.com/boakley/brackets-robotframework) for the
brackets editor. I could use the API to find out which features users
are using the most, and if any features are going completely
unused. 


## Tip of the iceburg

This is just the tip of the iceberg. Not even that -- it's an ice cube
in a glass of tea that is sitting on the tip of an ice berg. The
possibilities really do seem endless. The videos showed me where the
tin can api was used in a childrens museum, on a firing range with US
soldiers, in mobile apps, websites, gamification, compliance, and the list
goes on. 

## Can an API change the world?

Can an API change the world? Maybe that's an outlandish thing to
say. However, the Tin Can API has the potential to enable some really
amazing things in the years to come. Right now I am very envious of
the people working in the e-learning space because the Tin Can API is
very cool.



