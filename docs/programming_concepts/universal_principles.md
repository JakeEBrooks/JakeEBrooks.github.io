---
layout: default
title: "Universal Principles"
permalink: "/docs/programming_concepts/universal_principles"
parent: Programming Concepts
nav_order: 2
---

## Universal Principles
There are some ideas that are common across all languages, so I thought I'd better go over these as they're often yet another thing that gets left out of introductory materials for programming. Again, they might seem simple, but having an explicit understanding can simplfy things in the long run. Where I can, I'll give concrete, intuitive, and simple examples using Python.

### How do you actually write programs?
Most often in just a simple text document. You install the necessary software for the programming language you're using, point it at the text file you created, and the software will read through the file assuming it contains code written in the language it understands. For it to do this, the words and letters you type in the text file to make the program must follow a set of rules, collectively called the languages _syntax_.

### Syntax
You actually already understand what syntax is, even if you've never thought about it before. That is, assuming you speak a language, which I hope is the case since you're reading this in English (right?).

Syntax just means the rules of a language, which includes spoken languages. When I was learning German, for example, I could never understand why, when speaking in the past tense, the verb of the sentence goes to the end:

> I **love** Programming! = Ich **liebe** Programmieren!

> I **loved** Programming! = Ich habe das Programmieren **geliebt**!

_Like, it's just one letter... sigh_

English has rules like this too, and most of us are pretty good about following them. For example, someone might say "Programming love I!". This is grammatically incorrect; the words aren't following the rules of English. In other words, the initial statement did not follow the rules of English and was, therefore, using incorrect syntax.

Programming languages have similar (mostly simpler) rules and unfortunately you just have to learn them. This will come naturally as you practice writing programs in whatever language you're using, so don't lose patience and keep at it; understanding will come.

### Program flow
This is one of the most overlooked concepts in programming because anyone with enough experience won't think twice about it. Nevertheless, I think it's worth laying out explicitly.

So when you're writing a program, you're just typing words into any old text file which the software associated with the programming language will then read later on. If you've written everything following all the rules of that programming language it will translate everything you wrote into something the machine can understand, and you can run the program. Generally speaking, the software that does the translation (called [the compiler](https://en.wikipedia.org/wiki/Compiler)) will read the lines in your text file **in the order they were written**. I won't go into this any further, but it is a crucial concept to bear in mind as we start writing longer programs.

### Data types
*Might I suggest taking a break here? The next two sections are important, and rather lengthy... :)*

Remember when we talked about ASCII [in the first section](../fundamental_concepts/binary_numbers#representing-information-with-binary-numbers), and how binary numbers are mapped to alphabetical letters? Well there's a similar thing for regular base-10 numbers, but it gets a bit more complicated for a couple of reasons.

Binary numbers of a fixed bitwidth (a fixed number of binary digits) have a maximum representable base-10 number. For example, the maximum number you can represent with a nibble is `1111 = 16`, so if you want to represent a bigger number than sixteen, you need more binary digits. Remember also that our big binary storage book (like a hard drive) can only hold a certain number of binary digits, therefore bigger base-10 numbers take up more storage space.

Furthermore, for practical reasons, we need to be able to represent *any* ***real*** *number* in a computer. This gets tricky because this would also mean we need an infinite number of binary digits to represent some numbers. Take the well known irrational number $\pi$:

$$\pi = 3.141592653589793.....$$

How could you represent this number using binary? Without an infinite number of binary digits, you can't, just like how it takes an infinite number of normal digits to measure $\pi$ with 100% accuracy. This leads nicely into the idea of **data types**. A data type primarily answers two questions:

- What is this collection of binary digits representing? An integer? A decimal value? A letter? An address?
- How much storage space do you need to represent this value? A bit? A byte? A kilobyte?

By defining data types, we create a universal rulebook on how we can go from binary to something we humans can understand. There's a huge number of data types out there, and most programming languages will allow you to define your own if you wanted to. But you really only need an understanding of the three big ones:

- **Integers**: Integer numbers, like 12345
- **Floats**: Numbers with a decimal point, like 12.345
- **Strings**: Letters or sequences of letters, like "abcdefg"

Most other data types will be similar to these, or even use them in some way. Defining these three data types answers the question of "What?", but we still need to answer the question of "How?". We've already looked at how to encode letters as binary numbers, next we'll look at how we can represent Integers and Floats in practice.

### Integer & Float Precision
So we know that we can't (practically) use an infinite number of binary digits to represent numbers, which means we have to draw the line somewhere. Where we draw this line, or in other words, how many binary digits we allocate, is called the data type's **precision**. A data type that uses more binary digits will have a greater **precision** than a data type that uses less binary digits. How the data types are implemented varies from language to language, but I'll take you through two examples just to illusrate what goes on behind the scenes.

#### Integers
Integer data types come in two forms: **signed** and **unsigned**. A signed integer just means that it has a + or a - attached to it, so signed integers can be used to represent negative numbers. Each of these signed and unsigned variants will usually come in powers of two, most often up to 64 bits. Telling the computer you want to use a 64 bit unsigned integer, for example, means it will carve out 64 spaces for 64 binary digits, and this will allow you to store any integer value up to the number $2^{64}$, the result of which I won't vandalise your screen with. Suffice to say it's a *really big number*.






### Functions

### Loops

### Objects

### Metaprogramming