---
layout: default
title: "Loops"
permalink: "/docs/programming_with_mojo/loops"
parent: Programming with Mojo
nav_order: 3
---

# While Loops
I'll start right away with a warning about While loops. The whole point of a While loop is that it will keep executing the same block of code until some condition is met. So, if for some reason the condition is never met, then _it will loop forever_. It won't damage your computer, but it will mean you have to manually terminate it, normally using Ctrl+C.

With that said, let's write some code. The problem we're going to be solving in this section is finding the sum of all multiples of $$3$$ or $$5$$ below the number $$1000$$. For example, the numbers that fit this criteria below $$10$$ are $$3$$, $$5$$, $$6$$, and $$9$$. So the result would be $$3 + 5 + 6 + 9 = 23$$.

We'll start off by first making a function that tells us if a number `X` is a multiple of number `Y`. This is going to return a [boolean value](../fundamental_concepts/boolean_logic) and we'll also need an [If statement](../programming_concepts/universal_principles#if-statements). And lastly we're going to use the __modulo__ operator, `%`, which performs a divison operation and returns the remainder. So for example, the result of `3 % 2` is `1`, and the result of `24 % 7` is `3`. Therefore, if `X` is indeed a multiple of `Y`, then the result of `X % Y` should be `0`.

Have a go at writing the following function using these ideas:

```python
fn is_multiple_of(X: Int, Y: Int) -> Bool:
    if X % Y == 0:
        return True
    else:
        return False
```

Once again let's break it down line by line. We're declaring a function called `is_multiple_of` that takes in two `Int`s `X` and `Y`. The function is going to return a `Bool` value which will either be `True` or `False`, as all boolean values are. On the first line inside the function, we are testing if the operation `X % Y` evaluates to `0` using the 'is equal to' operator `==`. If it does we `return True`, otherwise we `return False`. Note that you could also achieve the same thing using an `elif` instead of an `else` like so:

```python
fn is_multiple_of(X: Int, Y: Int) -> Bool:
    if X % Y == 0:
        return True
    elif X % Y != 0:
        return False
```

where we have instead used the 'is not equal to' operator `!=`. Though it is generally preferred to use `else` over `elif` where possible, to avoid a situation where neither condition is met and there is no fallback option.

Next, as always, we need a `main` function. The `main` function is going to use a `while` loop to test every number in the range $$1 <= n < 1000$$. If the test `is_multiple_of` comes back `True`, then we want to add that number to an overall total. So we're going to need to keep track of two numbers; one for the sum, and one for $$n$$. Try typing up the following `main` function beneath the `is_multiple_of` declaration:

```python
fn main():
    var n: Int = 1
    var total: Int = 0

    while n < 1000:
        if is_multiple_of(n, 3) or is_multiple_of(n, 5):
            total = total + n
        n += 1
    print(total)
```

And again, go through it line by line. An important detail here is the use of `var` instead of `let` to declare the variables `n` and `total`. Using `var` means that the variable's value can change, or in programming jargon, it is _mutable_. Don't worry about it too much for now, but just know that if you want a variable to change over time then it needs a `var`, if it's going to be the same at all points in the program then you want to use `let`.

The variable `n` is initialised to `1` (since dividing by zero causes the Earth to explode), and the total is initialised to `0`. The condition for the `while` loop translates literally: `while n < 1000` _loop over the code in the indented block underneath_. The first line of the loop tests whether `n` is a multiple of `3`, `or` a multiple of `5` (remember the [truth tables](../fundamental_concepts/boolean_logic#or)). If either one of (or both of) the calls to `is_multiple_of` returns `True`, then the program will execute `total = total + n`. Regardless of the if statement, at the end of every loop we increment the number `n` by one for the next loop. Finally, once the condition $$n >= 1000$$ has been reached, the loop no longer executes and the program moves on to the final instruction to `print(total)`. 

So for clarity, you should have typed out the following code in a Mojo file:

```python
fn is_multiple_of(X: Int, Y: Int) -> Bool:
    if X % Y == 0:
        return True
    else:
        return False

fn main():
    var n: Int = 1
    var total: Int = 0
    while n < 1000:
        if is_multiple_of(n, 3) or is_multiple_of(n, 5):
            total = total + n
        n += 1
    print(total)
```

and if all is well you should get back a result:

> 233168

Job done! It's important to watch your indentations in this example; indentation is how Mojo tracks what code belongs to which statement, and incorrect indentation will cause errors.

# For Loops
The other major type of loop is a For loop.