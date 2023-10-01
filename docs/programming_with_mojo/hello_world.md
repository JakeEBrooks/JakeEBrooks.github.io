---
layout: default
title: "Hello World!"
permalink: "/docs/programming_with_mojo/hello_world"
parent: Programming with Mojo
nav_order: 1
---

# Hello World!
It's a tradition when learning something new in programming to make the most basic program possible to make sure everything is working correctly. This is the "Hello World" program that just prints some text "Hello World!". So let's do that in Mojo. When writing Mojo in script form (as in, inside a text file) you need to tell the Mojo compiler what exactly you want to execute. This is the purpose of the `main` function. So to write our first program, simply write in a text file:
```python
fn main():
    print("Hello World!")
```

Then save that text file in the local directory as "hello_world.mojo". Now to run the program type at the command line:

```
mojo hello_world.mojo
```

If all is well, you should get back some text:

> Hello World!

And that's your first program! You typed some text in Mojo syntax and pointed the Mojo software at it. It then scanned through the file, compiled and then executed the code that you typed, which was supposed to print "Hello World!".

Now we'll go a bit deeper [and start writing some functions](./functions_in_mojo).