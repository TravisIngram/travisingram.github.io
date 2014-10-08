---
title: Updating Bundler
layout: post
summary: A brief post about how to update the Ruby gem Bundler.
tags: Environment Ruby Bundler
---

#### Bundler

[Bundler](http://bundler.io) is a tool designed to help manage dependencies within Ruby applications.  It allows developers to specify the [gems](http://rubygems.org) needed to run an application and then installs and tracks them for each environment; development, staging or production.  It's a pretty important tool for many Ruby developers, one that should be kept up-to-date.
The [latest version](http://bundler.io/v1.7/whats_new.html#version17), 1.7.3, is a security release meant to fix a potentially vulnerability.

Before updating, it might be a good idea to verify what version you're currently running.  If it's been a while, looking over the [change-log](https://github.com/bundler/bundler/blob/master/CHANGELOG.md) might be prudent.  While unlikely, it's possible that aspects of how the tool works were changed in intervening releases.
It's better to be sure you're aware of what's changed than find out after the fact.

```bash
bundle version
```

![Blunder version](http://cl.ly/image/1d2L3W1k0M3g/bundle_version.jpg "Bundler version")

#### Updating

But how do you update Bundler?

This may seem like a simple question, a basic question that anyone using Bundler ought to know.  I didn't, though.  And I spent what might be considered an embarrassingly long time trying to figure it out.
The problem is, when you use a tool on a near daily basis to install or update gems, it's easy to forget there are other ways to install and update gems.

In this case, to update Bundler simply run the following command.

```bash
gem update bundler
```

Once complete, you'll have the latest version and be able to move on.
