---
layout: default
title: "Boolean Logic"
permalink: "/docs/fundamental_concepts/boolean_logic"
parent: Fundamental Concepts
nav_order: 2
---

# Boolean Logic
Because there is only two unique digits in binary numbers, binary ends up crossing over quite nicely with an entire branch of algebra called [Boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra), developed by English mathematician George Boole _(those mutton chops!)_ about 170 years ago. The foundation of Boolean algebra is the idea that something is either **True** or **False**.

Boolean logic is one of those things you can start to see everywhere, if you look. Is your computer screen turned on? Hopefully, the answer is yes, so the statement "Your computer screen is on" evaluates to **True** in Boolean algebra. You can see the natural extension to a simple "Yes" or "No" response to a question. Here's some more _totally not sarcastic_ examples:

| Statement                                                                            | Boolean  |
|:-------------------------------------------------------------------------------------|:---------|
| Yorkshire Tea<sup>TM</sup> is the best brand of English tea                          | **False**|
| It is a good idea to guess the airspeed velocity of an unladen swallow               | **True** |
| I am enjoying vague Monty Python references                                          | **True** |
| I am understanding everything Jake is explaining to me                               | **True** |
| I am having the absolute time of my life reading through this **amazing** guide      | **True** |

... you get the idea. The crossover with binary comes in by asserting that:

`1 = True`\
`0 = False`

This equivalence is precisely the reason computers can make **decisions**. Rather than you, the human, telling the computer what to do at every possible point, it can instead be given the ability to make a choice, or series of choices, based on any number of criteria, independent from you. 

To understand how critically important this is, let's recognise for a moment that your brain does the exact same thing! You couldn't function properly if it didn't. I am drinking a cup of tea as I'm writing this, but when I take a sip, am I consciously ordering my hand to pick up the cup? Am I ordering my arm to move it to my mouth? No, instead I just have the urge to take a sip, and my brain handles the rest. Just like a computer based on Boolean logic, my brain has the ability to make decisions for me, just based on my urge to sip my tea. This means I can spend less conscious time on the mechanics of drinking tea, and just *decide* to drink it.

# Boolean Operations
Boolean truth values (**True** and **False**) have their own formalised set of operations that govern how they can be combined together, corresponding to logical decisions we make on a conscious and subconscious level every day of our lives. The result of each boolean operation is nicely encapsulated in a [truth table](https://en.wikipedia.org/wiki/Truth_table). Let's go through the three major boolean operators, **AND**, **OR**, and **NOT**. I'll show a truth table for each one.

## AND
Like it says on the tin, the result of this operator is calculated by considering one thing **AND** another thing:

| A        | B        | Result        | 
|:---------|:---------|:--------------|
| False    | False    | False         |
| True     | False    | False         |
| False    | True     | False         |
| True     | True     | True          |

So A and B must be **True** for the result to also be **True**.

## OR
Yeah believe it or not there's a recurring theme here. The **OR** operator considers one thing **OR** another:

| A        | B        | Result        | 
|:---------|:---------|:--------------|
| False    | False    | False         |
| True     | False    | True          |
| False    | True     | True          |
| True     | True     | True          |

So either A or B (or both) must be **True** for the statement to evaluate to **True**.

## NOT
This one is slightly different, since it only takes one input and returns the opposite, like so:

| A        | Result        | 
|:---------|:--------------|
| False    | True          |
| True     | False         |

It really is the ultimate contrarian!

All right, I'll leave it here for now. Boolean is really useful in programming, so of course we'll return to it later on. Next up, we'll be covering the basics of [what is actually inside your computer](./the_structure_of_your_computer).