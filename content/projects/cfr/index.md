---
title: "CFR Simultaneous"
description: "Finding optimal strategies in normal-form games using counterfactual regret minimization and monte-carlo sampling"
date: 2022-11-27
tags: ["c99", "statistics", "game-theory"]
draft: false
weight: 1
params:
  math: true

github: "https://github.com/remyCases/CFR_simultaneous"
---

## Motivation

This project was an attempt to work through [An Introduction to Counterfactual Regret Minimization of Todd W. Neller and Marc Lanctot](https://modelai.gettysburg.edu/2013/cfr/cfr.pdf) to have a better understanding on how strategies are found.

To be honest, it was also a way to learn how to find optimal strategies on boardgames.

## Content

This project covers two examples of normal-form games: `Rock-Paper-Scissor` and `Colonel Blotto`. While RPS was a simple example to learn the basics, Colonel Blotto is a more complicated (while still being played in a single simultaneous turn).

### Objective

The aim of this implementation is to find an optimal (mixed) strategy using CFR and monte-carlo sampling which consists of four parts:

1. computing utility of all pure strategies
2. draw a random action
3. accumulate regret
4. compute average strategies

Then steps 2 to 4 are repeted several times to achieve convergence.

If you need more information about these steps, you can find valuable information in [the linked PDF](https://modelai.gettysburg.edu/2013/cfr/cfr.pdf).

## Example: RPS

It is expected there is no optimal strategy in RPS aside a random one. The solver finds the following optimal strategy:

```markdown
Executing Monte-Carlo CFR for 100000 steps with seed 1
Nash strategies :
Action    player 1        player 2
ROCK      0.3347622       0.3366166
PAPER     0.3332283       0.3311550
SCISSOR   0.3320096       0.3322284
```

which is consistant which the theory. Thanks to this little project, I will be a better RPS player.

## Example: Colonel Blotto

### Rules

Colonel Blotto is a simple game. There are B battlefields and each player has S soldiers that they will simultaneously place. Then for each battlefield, the player with the most soldiers will win it, and the winner will be the one that wins the most battlefields.

Some obviously bad strategies is to place all soldiers in one battlefield. Of course you will win it, but you will loose all other ones (which is bad if there are more than 2 battlefields).

### Counting

While the bulk of the algorithm is still the same, the main difficulty here is to count all pure strategies. One can show there are ${B+S-1\choose B-1}$ pure strategies (it's a star and bar problem).
