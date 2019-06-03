---
layout: post
title: "Episode 9 - A better REPL"
image: '/assets/img/episodes/Episode 09.png'
ytvideo: QwZuY1dExAc
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
category: 'tutorial'
tags:
- vuejs
- jekyll
- blog
twitter_text: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
introduction: Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
---

## Completed items

This episode doesn't have much to do with compiler building. We just made the
REPL a bit easier to use. This includes the ability to edit multiple lines, have
history, and syntax highlighting.

## Interesting aspects

### Two classes

The REPL is split into two classes:

* [Repl] is a generic REPL editor and deals with the interception of keys and
  rendering.
* [MinskRepl] contains the Minsk specific portion, specifically evaluating the
  expressions, keeping track of previous compilations, and using the parser to
  decide whether a submission is complete.

I haven't done this to reuse the REPL, but to make it easier to maintain. It's
not great if the language specific aspects of the REPL are mixed with the
tedious components of key processing and output rendering.

## Document/View

The REPL uses a simple document/view architecture to update the output of the
screen whenever the document changes.

[Repl]: https://github.com/terrajobst/minsk/blob/69123841304be0b9be0c5dc451c20fa07742f567/src/mc/Repl.cs
[MinskRepl]: https://github.com/terrajobst/minsk/blob/69123841304be0b9be0c5dc451c20fa07742f567/src/mc/MinskRepl.cs