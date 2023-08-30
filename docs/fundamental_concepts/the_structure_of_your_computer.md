---
layout: default
title: "The Structure of your Computer"
permalink: "/docs/fundamental_concepts/the_structure_of_your_computer"
parent: Fundamental Concepts
nav_order: 3
---

## The Structure of your Computer
I really can't stress enough how much a basic awareness of the computers hardware will help you on your programming journey. This includes having at least a basic understanding of (in my opinion) the three following hardware components:

- The Central Processing Unit (CPU)
- The Graphics Processing Unit (GPU)
- Random Access Memory (RAM)

Let's dive into each of these components.

### The Central Processing Unit (CPU)
The CPU is, bluntly, where all the actual work happens in the computer (not _always_ true these days). Need to add two numbers? Send them to the CPU. Need to compute an __AND__ operation? That's a job for the CPU.

Everything a CPU can do is determined by its [instruction set](https://en.wikipedia.org/wiki/Instruction_set_architecture), which is best thought of as just a big instruction manual. You send to the CPU a piece of data, like a binary number, order it to perform one of the operations in its instruction manual on that bit of data, and then it will give you back the result. The CPUs instruction set, therefore, provides the fundamental building blocks of the entire computer. Everything your computer can do, can be boiled down into a series of instructions to the CPU with the necessary accompanying data (this is actually what happens in practice as well, we'll get to how that happens).

### The Graphics Processing Unit (GPU)
Once you've understood the CPU, the GPU is actually quite simple: it's effectively a CPU with a different instruction set. The instruction set of a GPU is specifically designed to be faster for operations associated with... well... graphics.

To demonstrate how it does this, consider the following operation:

`1 + 2 + 3 + 4 + 5`

To perform this calculation on a CPU you would have to break it down into four separate operations, because the add instruction only takes in two bits of data, so:

`1 + 2 = 3`\
`3 + 3 = 6`\
`6 + 4 = 10`\
`10 + 5 = 15`

Each of these operations takes a finite amount of time to compute, so the total time to perform the overall operation scales with how many pairs of numbers you need to add together.

If you wanted to make this operation faster, you could design an instruction set with an add instruction that, on a fundamental hardware level, accepts five numbers instead of two. In this case, you could compute `1 + 2 + 3 + 4 + 5` all in one go, and the operation would scale beyond that for every five numbers instead of every two numbers. This makes large summations faster.

That's a toy example, and not realistic, but the principle is exactly what happens in GPUs. The idea of utilising certain instructions for certain tasks is becoming more and more important in programming.

### Random Access Memory (RAM)
Random Access Memory is almost exactly the same as the big storage book we discussed at the end of the section on [binary numbers](./binary_numbers). It can still be thought of as a big book that you can write a bunch of binary numbers in, but the book is only so big so only so many numbers can be contained in it at one time. The key difference is that RAM is __temporary__ storage. As my teacher put it to me: 'if hard drives are the bookshelf, RAM is the reading table'. As long as the device is powered, anything stored in RAM can be accessed at will. Once power is shut off though, the data is lost forever. You can also think of RAM as the staging ground for the CPU, as often data is read from permanent storage into RAM, then from RAM into and out of the CPU (which performs some operation on the data), and then back into RAM.

It is generally quicker to access data contained within RAM for a few reasons, which I won't get into here. The take away point is that storage devices like hard drives, are _permanent_ but _slow_. RAM is designed to be _fast_ and _temporary_.