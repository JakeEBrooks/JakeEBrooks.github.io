---
layout: default
title: "The Two Language Problem"
permalink: "/docs/programming_concepts/the_two_language_problem"
parent: Programming Concepts
nav_order: 3
---

# The Two Language Problem
You might have noticed that I've only been using code examples written in Python and C. However, this guide is actually going to be teaching you a different language: Mojo. So why have I used Python and C examples if I'm actually going to teach Mojo? 

Unfortunately for you, there is a long story behind this and I'm going to tell it.

*Seriously though there's important historical context here that will help you understand the reasons that Mojo exists and the problems with the current paradigm of programming languages ok I'm going to tell the story now pls enjoy ok thanks*

---

I'm going to assume that you, dear reader, are fairly young and don't remember what computers were like when they first started popping up in the later decades of the 20<sup>th</sup> Century. Well neither do I, but I'm told they were quite a pain in the arse. Whereas today we carry around more computing power in our pockets than it took to send a team of three men into space to land two of them on the frickin moon, for a long time computers were big, expensive, complicated, and not that powerful (in relative terms). However, throughout the 1970s some clever folks in New Jersey US, working at Bell Labs, were trying to make things simpler. From the combined efforts of [Dennis Ritchie](https://en.wikipedia.org/wiki/Dennis_Ritchie), [Ken Thompson](https://en.wikipedia.org/wiki/Ken_Thompson), and [Brian Kernighan](https://en.wikipedia.org/wiki/Brian_Kernighan), we got the C programming language and the [Unix](https://en.wikipedia.org/wiki/Unix) operating system.

{: .text-center .fs-3}
![](../images/dr_kt_bell_labs.jpg)\
*A famous picture of Dennis Ritchie (left) and Ken Thompson (sitting) pictured at Bell Labs in front of a large block of machinery you might call a computer. Source: bell-labs.com*

It's tough to communicate just how much these two developments have impacted the entire world. The C programming language is *everywhere* these days. In fact, I'd be willing to bet that at least one item in the room you're sitting in right now runs on C, or some version of it. For good reason, Dennis, Ken, and Brian are seen as pioneers in the field of computer science, just because of the sheer amount of technology that has been developed in the last several decades that is based on C and Unix.

So for quite a while, C became the default programming language. If you were a computer scientist of any merit, you knew how to write programs in C (or it's later iteration, [C++](https://en.wikipedia.org/wiki/C%2B%2B), developed by [Bjarne Stroustrup](https://en.wikipedia.org/wiki/Bjarne_Stroustrup)), or at the very least knew *of* it. Attempts at replacing the C paradigm were frequent, but for a long time C remained stubbornly rooted at heart of programming. There's a number of reasons for this, but really only two are salient: 

- It's *fast*
- Everyone else uses it

Most software wants to execute as fast as possible because Humans are notoriously impatient buggers and don't like waiting around, so C is good for this. Plus, if everyone around you is also using C it makes developing the software much easier because you're all speaking the same language (literally). Anyone that knows C, however, knows that it has a few downsides. It's difficult to learn because it is far from readable, in the sense that someone not intimately familiar with your code could look at it and understand roughly what is going on; C is notoriously opaque in that way. Some would say the most obvious downside is that it's just *old* (nearly half a century old). Think of how much computer hardware has changed in that time; we've gone from computers that could just about add some numbers together as long as the room is cooled well enough (hyperbolic, I know), to processing units that can produce simulations of the formation of an *entire galaxy*. And yet, we're still using the same fundamental programming language. Something isn't right there.

So this is where Python comes in to the story...

---

Python has actually been around for about as long as C has. It was developed in the early 1980s by the famous [Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum); the former Python BDFL (Benevolent Dictator For Life). Despite being around for so long, Python really started to take over from C in the mid-to-late 2000s. It operates quite differently from C because it uses an [interpreter](https://en.wikipedia.org/wiki/Interpreter_(computing)) instead of the more traditional [compiler](https://en.wikipedia.org/wiki/Compiler) that C uses. As such, Python has a number of advantages, but again they boil down to:

- It's easy to use and read
- Everyone else *also* uses it

So people like me who grew up in the Python environment remain stalwartly committed to it because we understand it and for the most part it *just works*.