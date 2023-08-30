---
layout: default
title: "What are Programming Languages?"
permalink: "/docs/programming_concepts/what_are_programming_languages"
parent: Programming Concepts
nav_order: 1
---

## Programming Languages
So now we have a basic understanding of what goes on inside our computer, we can start to understand exactly what you're doing when you write a program in one of the ridiculous number of programming languages available.

You could, in principle, write code in binary and pass it directly to the CPU. However, no sane person has time for that, and in the modern age we instead rely on layered abstractions. It sounds silly, but I understand this by imagining a general planning a war. It would be stupid for the general to go to every point on the front line, and individually order every person under his command to move here, or go there, or attack this. It just doesn't work that way. There's a hierarchy involved to simplify the process for the general, so they can spend their time where it is most valuable: planning the war. In just the same way, it's silly for you, the programmer, to move every individual byte to the required location, and combine them all using any number of instructions native to the CPU. To illustrate this, have a look at the following snippets of code:

(show a series of code snippets going from simple python code, all the way down to machine code)

Don't worry about understanding what is actually going on, but just pay attention to the reduction in size and complexity you get from layered abstractions. This is what allows you, the programmer, to make the best use of your time. How a programming language makes these abstractions to reduce the amount of code __you__ need to write is one of its key distinguishing features.