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

Even though, I almost work under MIT, I like the idea that someone could stumble upon my code and will immediatly look for the rest of the project. Well, I did it in the past, so I like the idea. The main problem is the lack of discipline, in all projects (without any exception) I forgot some headers.

## A simple solution

I like Lua. Simple, lightweight. It feels like home for a C dev like me. But I can't for the love of Knuth remember the syntax. No matter how many lines of (bad) lua code I wrote, I hard reset each times I push my commit.

So, Lua was a natural candidate for my go-to scripting language for quick and easy cli tools.

## How I almost wipe out my hard drive
