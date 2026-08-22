---
title: "Writing cli tools for fun"
description: "Why writing your own cli tools is always a fun things to do"
date: 2026-05-10
tags: ["lua", "cli", "complete project"]
draft: false
weight: 1

toc: true

links: [
    {link: "https://github.com/remyCases/HeaderChecker", name: "GitHub - HeaderChecker"},
    {link: "https://github.com/remyCases/adventOfCode", name: "GitHub - AdventOfCode"},
]
---

## A simple problem

It usually starts with a single task to be done. Single, simple that can be done by hand. For instance, I try to add a three-lines header for each file of any projects I work on.

```txt
# Copyright (C) 2023 Rémy Cases
# See LICENSE file for extended copyright information.
# This file is part of adventOfCode project from https://github.com/remyCases/adventOfCode.
```

Even though, I almost work under MIT, I like the idea that someone could stumble upon my code and will immediatly look for the rest of the project. Well, I did it in the past, so I like the idea. The main problem is the lack of discipline: in all projects (without any exception) I forgot some headers.

## A simple solution

I like Lua. Simple, lightweight. It feels like home for a C dev like me. But I can't, for the love of Knuth, remember the syntax. No matter how many lines of (bad) lua code I wrote, I hard reset each times I push my commit.

So, Lua was a natural candidate for my go-to scripting language for quick and easy cli tools.

## How I almost wipe out my hard drive

An attentive reader would say the last part was some kind of foreshadowing and it certainly was. My script was simple, open a file, check if the header is here, if it's correctly formatted and return a log message to the console. As you may guess, in my first iteration I was opening files in *write* mode.

To celebrate my newly written tool, I run it throught my drive where I stored locally all my projects. Until I noticed the code of my script disappeared in front of me. It was not a trick of my IDE, no, it was a simple deletion of the script. All scripts. All LUA, python, C, C#, Rust, Nim, ... files gone.

I did lost some early prototypes I've never pushed. But I'd say 95% of all my work is on my GitHub. That's a good lesson, I guess.

## I still write some LUA scripts

It's been six months now, and I feel more and more spontaneously comfortable with LUA. I recovered mentally from that horrific event, but I still stress a little when I use `HeaderChecker`.

But my main issue is that I don't find any good reasons to work with LUA. In all my group projects, nobody wants to see any line of LUA, people want to maintain some python. I try to convince them that LUA is lightweight, really easy to write... It does not work. At least, it works on me. The only hope I have is that the next time I need to create a simple task, a simple checker, a simple thingy, LUA would there, waiting to wipe out my hard drive once again.
