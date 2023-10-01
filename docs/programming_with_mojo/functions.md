---
layout: default
title: "Functions"
permalink: "/docs/programming_with_mojo/functions"
parent: Programming with Mojo
nav_order: 2
---

# Functions
Functions are one of the foundations in programming, and good programmers know when and when not to use them. Recall from the [universal principles](../programming_concepts/universal_principles#functions) section that a function is a block of code that takes in some stuff, and based on that stuff outputs some other stuff. It really is as simple as that.

You actually wrote your first function in the previous section, called `main`. But that is a bit of a special case because the Mojo compiler is specifically looking for a `main` function with no inputs, so it knows where to start running from. In this section we'll write our own functions, starting with a function to add two numbers.

Before that I need to clarify something; there is actually two ways of writing functions in Mojo, for reasons related to the [Two Language Problem](../programming_concepts/the_two_language_problem). You can declare a function using either `fn` or `def`. Using `def` means you are using the Python style of functions, which are a lot looser and more relaxed about stuff like declaring data types. Using `fn` means you are using a more C-like style, so you need to give the compiler a lot more information, which you'll see in due course. Each has its upsides and downsides, but in general `def` is simpler but slower, and `fn` is more complicated but faster. I'll almost exclusively be using `fn` because `def` is simpler, so by learning to use `fn` it'll be much easier to switch to `def` if you have to.

To write a function to add two numbers using `fn`, we need to do a couple of extra things: we need to let Mojo know what inputs and variables there are and what data types they are. So write the following in a Mojo file:

```python
fn addints(a: Int, b: Int):
    let c: Int = a + b
    print(c)

fn main():
    addints(3, 4)
```

There's a lot to unpack there so let's go through it line by line. We need to declare all our functions before `main` so Mojo knows what it's supposed to do when it gets to `main`. In the first line we declare a function called `addints` using `fn`. This function takes in two `Int`s (integers) called `a` and `b`. In the second line, we declare an `Int` variable called `c` using `let` and initialise it with the value of `a + b`. In the third line, we finish the function by `print`ing the variable `c`. Now, when the compiler reaches the function call `addints(3, 4)`, it knows what to do because we've declared it beforehand!

There's also other ways we can complete the same objective. The following examples give the exact same result:

```python
fn addints(a: Int, b: Int):
    print(a + b)

fn main():
    addints(3, 4)
```
which allows us to do away with declaring `c` at all.

```python
fn addints(a: Int, b: Int):
    let c: Int
    c = a + b
    print(c)

fn main():
    addints(3, 4)
```
where we separate initialising the variable `c` and giving it a value into two lines.

Now is where I'm going to start encouraging you __to try breaking things__. Sometimes when people start programming they are afraid to make mistakes for fear of breaking the computer. __This is extremely unlikely__. Don't be afraid, and start tearing your program apart. The Mojo compiler is pretty good at giving reasonable error messages, so just like people take car engines apart and put them back together again, I encourage you play around with the code above and see what breaks! For example, you might want to see what happens if you just remove `let` from the declaration of `c` within the `addints` function. If you do, you'll get the following error message:

```
error: use of unknown declaration 'c', 'fn' declarations require explicit variable declarations
    c: Int
    ^
error: statements must start at the beginning of a line
    c: Int
     ^
mojo: error: failed to parse the provided Mojo

```

Nothing actually happened because the Mojo compiler is clever and detected the missing variable declaration. Once you've finished tearing apart the above program, come back and we'll start writing some more complex functions...

---

So the problem with the functions above is that we didn't actually get anything back from them. That's fine if that's what you want your function to do, but it means that if we wanted to do something further with the result of the `addints` function we couldn't do it. We can slightly modify the function to `return` the value of `c` instead of just `print`ing it. Try typing up the following:

```python
fn addints(a: Int, b: Int) -> Int:
    return a + b

fn main():
    let c = addints(3, 4)
    print(c)
```

Now this is slightly more useful! We've added the `-> Int` to the function declaration to let the compiler know that the function will be returning an `Int` whenever it is called. And the beauty of functions is that we can reuse the same code again and again...

```python
fn addints(a: Int, b: Int) -> Int:
    return a + b

fn main():
    let c: Int = addints(3, 4)
    let d: Int = addints(5, 10)
    let e: Int = addints(297, 100)
    print(c)
    print(d)
    print(e)
```

which prints:

>7\\
>15\\
>397

_Easy. As. Pie._

Speaking of pie... or $$\pi$$, if we wanted to use decimal numbers (or [floats](../programming_concepts/universal_principles#data-types)) we only need to make a few modifications. Let's modify (and appropriately rename) the `addints` function to take in two floats and return one float instead:

```python
fn addfloats(a: Float32, b: Float32) -> Float32:
    return a + b

fn main():
    let c: Float32 = addfloats(4.3, 9.2)
    print(c)
```

Will give us:

> 13.5

Note that we've specifically used 32-bit floats here, which will be fine [up to a certain level of accuracy](../programming_concepts/universal_principles#integer--float-precision)

Ok, we've covered everything you need to start writing basic functions. It isn't everything and there's plenty more to learn, but _Rome wasn't built in a day_. Next we'll do a similar overview of [loops](./loops).