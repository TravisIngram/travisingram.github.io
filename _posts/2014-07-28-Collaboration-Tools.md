---
title: Collaboration Tools
layout: post
date: 2014-07-28
---

### 20140728 - Original Post

Here are some basic collaboration tools that I've found can come in handy when needing to work remotely with others.  Most are pretty straight forward and friction free in their use.  These are primarily geared towards situations where you need some quick feedback or are working through an exercise or project with your peers.

The site [Pair Program with Me](http://www.pairprogramwith.me) is another great resource and offers many additional options.

If you have other tools you’ve used and find useful, please don't hesitate to share them!

===

### Google Hangouts

[Google Hangouts](https://www.google.com/hangouts/) offer a convenient way for individuals and groups to meet up and talk.  They have been integrated throughout most of Google's services and can be accessed in Gmail, Google Plus, Voice, or individual apps for iOS and Android.  In addition to audio, video, chat, and screen sharing, the platform offers numerous plugins (like Floobits) that expand its basic functionality.  The [Zapier](https://zapier.com/blog/google-hangouts-video-calls-guide/) link below is a great overview of the service and its user interface.  It also does a nice job of detailing the numerous ways to go about initiating a call.

To take advantage of [Google Hangouts](https://support.google.com/hangouts/#topic=2944848), you'll need to have a Google account and install the [plugin](https://www.google.com/tools/dlpage/hangoutplugin) on your browser of choice.

Google Hangouts and the associated GTalk plugin are very resource intensive.  Laptop users should be mindful of their battery, chances are it won’t hold up over the course of a two hour session.  Anecdotal evidence suggests that Safari is slightly better in this regard than Chrome.

Here are a few basic best practices to keep in mind when interacting with others via Google Hangouts.

* **Always use headphones.**
  * The Apple earbuds with inline mic work well, a dedicated headset, even better.
* Background noise can be distracting and make it difficult to focus on the presentation.
  * Please be mindful of your environment.  Maintaining an open mic helps keep the communication flowing but excess noise is a distraction.  Use your best judgement when deciding to mute or not.
  * As a general rule, if you’re in a consistently noisy environment, like to fidget,  or are prone to snacking, it might be best. =]
  * If you are muted and need to talk, pressing `⌘ + d` (`ctrl + d` for Windows), will activate your mic.
* If you’re experiencing distorted audio or blocky video, it may be related to your connection.  Try reducing the quality via the [bandwidth icon](https://support.google.com/hangouts/answer/2979333) or [turning off](https://support.google.com/hangouts/answer/1254313?hl=en&ref_topic=2944918) your camera entirely.

**Resources**

* Zapier, [The Missing G+ Hangouts Guide](https://zapier.com/blog/google-hangouts-video-calls-guide/)
* University of Minnesota, [G+ Hangout Self-Help Guide](http://it.umn.edu/services/all/training-usability/self-help/self-help-guides/google-video-calls.html)
* Headset recommendation from The Wirecutter: [Microsoft LifeChat LX-6000](http://thewirecutter.com/reviews/best-usb-office-headset/)

#### Use case:

* Anytime you need convenient access to audio AND video AND screen sharing AND collaborative text editing.
  * If video isn't required, there might be better options, like one of the services listed below.

### ScreenHero

**ScreenHero has officially launched and is now a paid service.  It costs $10/mo. This makes me a little sad as I think that's a bit prohibitive for folks who just want to pair and aren't using it as a production tool.**

[ScreenHero](http://screenhero.com) is an application that enables remote collaboration through integrated voice / text chat and (surprise!) screen sharing.

One person acts as the host, sharing their screen with another, remote user.  A word of caution, though, the remote user will have full access to the host machine.  So when connecting as the remote, be mindful of where you’re clicking.  Thankfully, ScreenHero provides each user with their own labeled cursor.  Which makes it much easier to keep track of where you’re at and who is moving and typing.

In a typical session, you might be working on a file in Sublime Text or in the Terminal.  In either case, it’s easy to track who’s doing what and follow along.  When it’s time for the remote user to type (drive) they will be able to do so, albeit with some input lag.  Since there’s no video involved, at least in the traditional sense, the bandwidth required is much lower.  Especially when compared to something like Google Hangouts. Still, depending on the connection, there’s usually a brief delay when typing or clicking.  It can be a little disorienting at first but shouldn’t take long to get accustomed to.

~~ScreenHero is currently free to use.  It’s in beta, though, so the occasional bug might pop up.~~

~~It will move to a paid service in the coming weeks.~~

#### Use case:
* A great tool if you don't require video and don't mind hosting or connecting to another user.

### Floobits

[Floobits](https://floobits.com) is a collaborative text editor and screen sharing solution. It’s primarily intended for folks who need to remotely pair program but has a number of features that make it appealing for small groups as well.  See the link below for a full description.

**Resources**

[**Working with Floobits locally**](https://travisingram.github.io/2014/08/10/2014-08-10-Floobits-Locally)

### Stypil

[Stypi](https://code.stypi.com/) is a realtime text editor that enables quick collaboration on a shared documents.

It’s a handy alternative to something like ScreenHero or Floobits if you just want to quickly connect and work through an exercise.  It also has many of the basic features you’d expect from a text editor.  It offers syntax highlighting for a number of programming languages such as Ruby, HTML, CSS, and Javascript.  It also allows you to set up the appropriate tab distance and has a few built in themes like Monokai and Solarized.  If you register for an account it will store your documents and settings for later sessions.

**Resources**

Here’s a short [tutorial](http://vimeo.com/76870082) for basic Stypi use.

#### Use case:
* Since it doesn't have integrated voice chat, you'll need to use another application for that.  But it's a good choice if, for whatever reason, you don’t want to share your own environment or make a direct connection to someone else machine.
* For those with an account, saving files and being able to continue working on an exercise is pretty convenient.

### CloudApp

[CloudApp](http://www.getcloudapp.com) is an application that allows you to quickly upload and share screenshots.  It can be quite useful when debugging and you want to share an error message.

#### Use case:
* Any situation where you need to quickly share an individual screenshot.
* If you upgrade your account you can also store and share video files.

### Hastebin

[Hastebin](http://hastebin.com/about.md) is a simple site that allows you to quickly save and share code snippets.  It even has a [gem](https://github.com/seejohnrun/haste-client) that, once installed, will allow you to use it from the command line.

#### Use case:
* This site makes it easy to share code.  It's a quick way to send off a link for review or feedback.  The recipient can review and edit as needed and provide feedback inline.

### GitHub Gist

[GitHub Gists](https://gist.github.com), much like Hastebin, is a great way to quickly save and share code snippets, full documents, or multiple files.  They are also able to be forked and cloned, just like a regular git repository.

#### Use case:
* This site makes it easy to share anything ranging from a single snippet to multiple files.  It offers a quick way to disseminate information and do so in a private way.  Unlike Hastebin, people aren't able to make inline comments, so Gists are a little less handy in that regard.  Overall, still a handy resource.

### SizeUp

[SizeUp](http://www.irradiatedsoftware.com/sizeup/) is a utility that allows you to quickly change the position of the currently active window.  It's very useful when screen sharing with someone else.

#### Use case:
* This utility makes it easy to quickly move and resize windows, especially during a pairing session.
