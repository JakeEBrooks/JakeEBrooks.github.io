---
layout: default
title: "Hello World!"
permalink: "/docs/programming_with_mojo/hello_world"
parent: Programming with Mojo
nav_order: 1
---

# Hello World!
It's a tradition when learning something new in programming to make the most basic program possible to make sure everything is working correctly. This is the "Hello World" program that just prints some text "Hello World!". So let's do that in Mojo. Open up a text file in your favourite text editor and type:
```python
print("Hello World!")
```

Then save that text file in the local directory as "hello_world.mojo", or if you're feeling adventurous save it as "hello_world.&#128293;". Now to run the program type at the command line:

> mojo hello_world.mojo

or

> mojo hello_world.&#128293;

If all is well, you should get back some text:

> Hello World!

And that's your first program! You typed some text in Mojo syntax and pointed the Mojo software at it. It then scanned through the file, compiled and then executed the code that you typed, which was supposed to print "Hello World!".

Now we'll go a bit deeper [and start writing some functions](./functions_in_mojo).