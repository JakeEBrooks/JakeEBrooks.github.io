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

Python has actually been around for about as long as C has. It was developed in the early 1980s by the famous [Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum); the former Python BDFL (Benevolent Dictator For Life). Despite being around for so long, Python really started to take over from C in the mid-to-late 2000s. It operates quite differently from C because it uses an [interpreter](https://en.wikipedia.org/wiki/Interpreter_(computing)) instead of the more traditional [compiler](https://en.wikipedia.org/wiki/Compiler) that C uses. This means that instead of looking at the whole program and translating it for the machine all in one go, it actually translates and executes each line of the program individually.

People like me who grew up in the rich Python environment remained stalwartly committed to it because we understand it and for the most part it *just works*. In my opinion, one of the greatest achievements of the Python era was to make programming in general far, far more accessible than it had been in the past. As programming languages go, Python is incredibly easy to understand. The focus on readable, simple to understand syntax is baked right into the Python philosophy, and the insight from Guido that 'code is read much more often than it is written' is one of the pillars of Python's success. This made it easier for people entirely unfamiliar with programming to learn it, because they didn't have to get over the harsh syntax present in languages like C/C++.

One of the other major advancements by the Python community was its vast package ecosystem. When you write code, you're often importing bits of other peoples code before you start writing your own so you don't have to waste time on implementing features not directly relevant to what you want to do. For example, as a radio astronomer I need to use lots of [fourier transforms](https://en.wikipedia.org/wiki/Fourier_transform), but I don't want to write my own code for doing the fourier transform because it would take a long time and someone else can implement a much better version than I can. So I import someone elses code to do a fourier transform and I can press on with what I originally needed to do. The incredible Python package ecosystem means that nearly all applications of programming already have a great deal of publicly available code so you can get started quicker.

So if you're not convinced yet, I'll explicitly state I really like Python. **But**, there are two big downsides to Python. Firstly, it is so, so, so very slow. It is the elderly, drunken sloth of the programming family. If you care at all about performance in your applications you don't use Python, you use C instead, or some other language. I'm not going to get into all the reasons *why* Python is so slow, but just imagine trying to bake a cake you've never made before, while *only* being given one step of the recipe at a time. It isn't the most efficient way to bake the cake. Because it is so slow, but it's also so commonly used, Python has become the default 'front end' for a huge number of applications. You, the user, will interface with the program through Python because it's easy to read and understand and it's friendly and all the error messages are clear and *blah blah blah*, but all the actual functionality of the software is written in fast, clean C code, that is more or less opaque to anyone except the small group of very clever people who wrote it. As I said, this is the approach for many popular software packages, including but definitely not limited to:

- [NumPy](https://numpy.org/), the default Python library for all maths related problems
- [SciPy](https://scipy.org/), the NumPy equivalent for scientific applications
- [Tensorflow](https://www.tensorflow.org/) & [PyTorch](https://pytorch.org/), the two most popular machine learning tools
- [CASA](https://casadocs.readthedocs.io/en/stable/), the most popular software package for radio astronomers

All of these tools want to be fast, so they don't actually write anything significant in Python, and instead outsource it to C or C++. The result is that, while Python is one of the most popular programming languages, it functions like a 'glue language' for sticking together many different bits of C code when performance is an issue (which it often is).

It actually gets worse... Up until now I've been talking about Python as a separate language that functions independently from C, but that isn't true. In actuality, Python is C. The Python interpreter itself, the thing that reads through your programs and executes code, actually translates your code into C first, which then gets translated into binary code by the normal C compiler.

So now, as we go into the 2020s, much of the cutting edge software development ecosystem is now in this strange situation where we're effectively still using C, *almost five decades after it was made*. There's an awkward dance that goes on between Python and C depending on what you're working on and who you're working with and on top of all this, applications are inheriting the fundamental problems of both C *and* Python. In this time, computer hardware has gone through a number of technological revolutions since that black and white picture of Dennis and Ken was taken all those years ago, but in the software world we can't seem to move on from C.

How this problem translates into the real world is a simple case of lost productivity. In our highly electronic and interconnected world, time is so unbelievably connected to money to an eye watering extent, that a two or three times speedup in software can be the difference between a massive multinational business conglomerate going bankrupt or turning a massive profit that year. And if that isn't enough to convince you (which to be honest it isn't for me), imagine how beneficial it would be for our planet if that same multinational business could shrink the size of its data centers by half, since the software they are running executes twice as fast. In the modern world, faster programs really do help save the planet, and it's something any software developer should deeply care about.

---

Fortunately for us all, some very smart people are aware of the problem and are doing something about it. There have been a number of attempts to shift the dominance of C through new programming languages like [Rust](https://en.wikipedia.org/wiki/Rust_(programming_language)), [Swift](https://en.wikipedia.org/wiki/Swift_(programming_language)), [Julia](https://en.wikipedia.org/wiki/Julia_(programming_language)), and most importantly for this guide [Mojo](https://en.wikipedia.org/wiki/Mojo_(programming_language)). One of the key features of Mojo is that, in an attempt to ease the transition away from Python/C, it is syntactically a superset of Python. Any program written using Python syntax can also be executed as a Mojo program.

This is precisely the reason I have chosen to make this guide about learning Mojo; you can essentially learn Mojo and Python **at the same time**, while also learning a modern programming language that aims to solve many of the longstanding problems in the community. So without further ado, [let's jump right into it]().