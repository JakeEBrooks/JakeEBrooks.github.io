---
layout: default
title: "Universal Principles"
permalink: "/docs/programming_concepts/universal_principles"
parent: Programming Concepts
nav_order: 2
---

# Universal Principles
There are some basic ideas that are common across all languages, so I thought I'd better go over these as they're often yet another thing that gets left out of introductory materials for programming. Again, they might seem simple, but having an explicit understanding can simplfy things in the long run. Where I can, I'll give concrete, intuitive, and simple examples using Python.

## How do you write programs?
Most often in just a simple text document: a fancy ".txt" file. You install the necessary software for the programming language you're using, point it at the text file you created, and the software will read through the file assuming it contains code written in the language it understands. For example, if you wanted to write a Python program, you would start by creating a text file called "hello_world.py", where the ".py" file extension just means: _this is a text file containing things written using Python syntax_. So inside the text file might just be:

```python
print("Hello World!")
```

There's a number of ways to actually run the program, but the most basic way that you'll be using a lot early on is from the command line, by typing:

`python hello_world.py`

with the "hello_world.py" text file in your local directory. The Python software will then look in the text file and execute the code within, which will just show on the screen:

> Hello World!

## Syntax
You actually already understand what syntax is, even if you've never thought about it before. That is, assuming you speak a language, which I hope is the case since you're reading this in English (right?).

Syntax just means the rules of a language, which includes spoken languages. When I was learning German, for example, I could never understand why, when speaking in the past tense, the verb of the sentence goes to the end:

> I **love** Programming! = Ich **liebe** Programmieren!

> I **loved** Programming! = Ich habe das Programmieren **geliebt**!

_Like, it's just one letter... sigh_

English has rules like this too, and most of us are pretty good about following them. For example, someone might say "Programming love I!". This is grammatically incorrect; the words aren't following the rules of English. In other words, the initial statement did not follow the rules of English and was, therefore, using incorrect syntax.

Programming languages have similar (mostly simpler) rules and unfortunately you just have to learn them. This will come naturally as you practice writing programs in whatever language you're using, so don't lose patience and keep at it; understanding will come. An example of these rules can be seen in Python:

```python
print(5)
```

will show on the screen the number 5. Whereas

```python
print{5}
```

using curly braces instead will throw an error and make Python very angry :(

## Program flow
This is one of the most overlooked concepts in programming because anyone with enough experience won't think twice about it. Nevertheless, I think it's worth laying out explicitly.

So when you're writing a program, you're just typing words into any old text file which the software associated with the programming language will then read later on. If you've written everything following all the rules of that programming language it will translate everything you wrote into something the machine can understand, and you can run the program. Generally speaking, the software that does the translation (called [the compiler](https://en.wikipedia.org/wiki/Compiler)) will read the lines in your text file **in the order they were written**. When it is reading line number ten in the text file, it **does not have any knowledge of what is further down the page, beyond line number 10**. I won't go into this any further, but it is a crucial concept we'll come back to in the future.

## Data types
*Might I suggest taking a break here? The next two sections are important, and rather lengthy... :)*

Remember when we talked about ASCII [in the first section](../fundamental_concepts/binary_numbers#representing-information-with-binary-numbers), and how binary numbers are mapped to alphabetical letters? There's a similar thing for mapping binary to regular base-10 numbers, but it gets a bit more complicated for a couple of reasons.

Binary numbers of a fixed bitwidth (a fixed number of binary digits) have a maximum representable base-10 number. For example, the maximum number you can represent with a nibble is `1111` which is the number sixteen, so if you want to represent a bigger integer number than sixteen, you need more binary digits. Remember also that our big binary storage book (like a hard drive) can only hold a certain number of binary digits, therefore bigger base-10 numbers take up more storage space.

Furthermore, for practical reasons, we need to be able to represent *any* ***real*** *number* in a computer. This gets tricky because this would also mean we need an infinite number of binary digits to represent some numbers. Take the well known irrational number $$\pi$$:

$$\pi = 3.141592653589793.....$$

How could you represent this number using binary? Without an infinite number of binary digits, **you can't**, just like how it takes an infinite number of normal digits to measure $$\pi$$ with 100% accuracy. This leads nicely into the idea of **data types**, which you can think of as a label for some collection of data. A data type primarily answers two questions:

- What is this collection of binary digits representing? An integer? A decimal value? A letter? An address?
- How much storage space do you need to represent this value? A bit? A byte? A kilobyte?

By defining data types, we create a universal rulebook on how we can go from binary to something we humans can understand. There's a huge number of data types out there, and most programming languages will allow you to define your own if you wanted to. But you really only need an understanding of the three big ones you'll see wherever you go:

- **Integers**: Integer numbers, like 12345
- **Floats**: Numbers with a decimal point, like 12.345
- **Strings**: Letters or sequences of letters, like "abcdefg"

Most other data types will be similar to these, or even use them in some way. Defining these three data types answers the question of "What?", but we still need to answer the question of "How?". We've already looked at how to encode letters as binary numbers, next we'll look at how we can represent Integers and Floats in practice.

## Integer & Float Precision
So we know that we can't (practically) use an infinite number of binary digits to represent numbers, which means we have to draw the line somewhere. Where we draw this line, or in other words, how many binary digits we allocate, is called the data type's **precision**. A data type that uses more binary digits will have a greater **precision** than a data type that uses less binary digits. How the data types are implemented varies from language to language, but I'll take you through two examples just to illustrate what goes on behind the scenes.

#### Integers
Integer data types come in two forms: **signed** and **unsigned**. A signed integer just means that it has a + or a - attached to it, so signed integers can be used to represent negative numbers. Each of these signed and unsigned variants will usually come in powers of two, most often up to 64 bits. Telling the computer you want to use a 64 bit unsigned integer, for example, means it will carve out 64 spaces for 64 binary digits, and this will allow you to store any base-10 integer value up to the number $$2^{64} = 18,446,744,073,709,551,616$$.

#### Floats
Float precision is more tricky, and has been and probably always will be, one of the core problems in computer science. 

The number 

$$20/7 = 2.8571428....$$

has an infinite number of digits in everyday mathematics. We've established, however, that an infinite number of digits is not an option when we're trying to store information in binary. So binary representations of numbers like $$20/7$$ will not be *completely* accurate. As a toy example, writing out $$20/7$$ as a float might look something like:

$$20/7 = 2.8571428$$

with all the extra numbers just ignored. However, if we then tried to some further computation we're going to run into problems because our initial data was not fully accurate. To try and make this more concrete, I'll define two numbers $$x$$ and $$y$$. One will be the float representation, the other will be the 'real' representation, so:

$$x = 2.8571428$$

$$y = 20/7 = 2.8571428....$$

If our float description, $$x$$, is fully accurate the following should be true:

$$x/y = 1.0$$

but actually, in practice, it might evaluate to something like:

$$x/y = 0.9999999999....$$

The discrepancy is known as a **floating-point error**. It can quickly escalate to nightmare levels if the problem isn't managed properly, since every further operation compounds the original error. For example, the operation $$x * 5$$ will have a further error of $$(y - x)*5$$.

So with that out of the way, let's move on to what goes on under the hood. Again, there's a huge number of ways to represent *any* real number, but as I understand it the most common method is to just use two integers like so:

$$5/2 = 2.5 = 25 \times 10^{-1}$$

So we've condensed the problem to just two integers instead; one for the actual number and one for the exponent of ten (which will always be negative). Here's another example:

$$9/8 = 1.125 = 1125 \times 10^{-3}$$

This means that all the restrictions we went through in the previous section on integer precision, *also* apply to floats.

*Ok we're done with this for now, take another break :)*

## Variables
If you're already familiar with algebra, variables should come quite naturally to you because they're almost exactly the same as algebraic numbers. Variables are how you communicate values to your program. Most languages require you to label your variables with data types so it knows roughly what it is going to be working with when performing operations.

Python isn't one of these languages, so you can define variables quite simply:

```python
x = 2
```

and it will automatically know you're talking about some kind of integer. In C, it's slightly different because the C compiler wants to know exactly what datatype your variable is in advance, so the same variable definition would be:

```c
int x = 2;
```

In both languages, anytime you type `x` the program will know you're actually talking about the integer number `2`.

## Functions
Functions are nice and (mostly) simple, and you should use them as much as possible. There are a number of reasons to make liberal use of functions, including making your program faster, but we'll get into that later.

Simply put, a function takes in *something*, and then performs a task using that *something*. The *something* it takes in can be anything, and it doesn't have to just be one thing; functions can take in as many *somethings* as you want them to. Say we want a function to add together *any* two integers. In Python this would look something like:

```python
def add(x, y):
    return x + y
```

In English, you can think of this as defining (```def```) a function called ```add```, that takes in two numbers ```x``` and ```y```. It then ```returns``` to the user the value of ```x + y```. In C, this same function definition looks a bit more horrible, but it's worth seeing the comparison:

```c
int add(int x, int y) {
    int sum = x + y;
    return sum;
}
```

Again, don't worry too much about every intricate detail of those examples. Just take away the principle of what functions do.

## Loops
Loops allow you execute the same code multiple times, or even continuously until some criteria is met within the program. For example, lets say I *really* like the number 3, and I want to write a python program to print 100 lines of the number 3. Instead of writing

```python
print(3)
print(3)
print(3)
print(3)
....
```

for one hundred lines, I can instead write:

```python
for i in range(100):
    print(3)
```

to get the same effect. There's two kinds of loops in programming: **for** loops and **while** loops. If you want to run some code a certain number of times, use a **for** loop. If you want to to run some code until something happens, use a **while** loop. Don't worry about every detail of the code examples, again, just remember the principle of a **for** loop vs a **while** loop.
