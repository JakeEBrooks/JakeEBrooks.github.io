---
layout: default
title: "What are Programming Languages?"
permalink: "/docs/programming_concepts/what_are_programming_languages"
parent: Programming Concepts
nav_order: 1
---

# Programming Languages
So now we have a basic understanding of what goes on inside our computer, we can start to understand exactly what you're doing when you write a program in one of the ridiculous number of programming languages available.

You could, in principle, write code in binary and pass it directly to the CPU. However, no sane person has time for that, and in the modern age we instead rely on __layered abstractions__, like an operating system. It sounds silly, but I understand this by imagining a general planning a war. It would be stupid for the general to go to every point on the front line, and individually order every person under his command to move here, or go there, or attack this. It just doesn't work that way. There's a hierarchy involved to simplify the process for the general, so they can spend their time where it is most valuable: planning the war. In just the same way, it's silly for you, the programmer, to move every individual byte to the required location, and combine them all using any number of instructions native to the CPU. To illustrate this, I'm going to show a series of code snippets that are functionally the same, but increase in complexity because we're stripping back some of the abstraction layers each time.

First have a look at this Python code:

```python
print("Hello World!")
```

which just prints "Hello World!" to the screen. Python is a very high level language, which means that it contains more layered abstractions than most languages. Next, here's the same code in C:

```c
#include <stdio.h>
int main() {
    printf("Hello World!\n");
    return 0;
}
```

which does exactly the same. We're typing out a bit more to do the same task because C is lower level language than Python (though still quite high in the grand scheme). Little things like defining a newline with a ";", or enclosing the function with curly braces "{}" are left to us to do. This helps the computer because it has less to figure out on its own (like when a newline begins), but is bad for us because we have to type more.

Ok, now let's jump a bit closer to the CPU with [assembly code](https://en.wikipedia.org/wiki/Assembly_language). Looking back over history, there was a time when computer scientists were actually passing binary numbers to the computers they had at the time. So binary code is considered the first generation of programming languages. As CPU technology progressed, and the tasks we wanted the computer to do got more complex, passing in binary code just stopped being a practical option. This lead to the development of assembly language; the second generation of programming languages. Assembly language is normally quite close to the instruction set of the CPU, and as you write assembly code you're directly referencing certain instructions. Here's the exact same code as above, but in assembly:

```
	.file	"hello_world.c"
	.text
	.section	.rodata
.LC0:
	.string	"Hello World!"
	.text
	.globl	main
	.type	main, @function
main:
.LFB0:
	.cfi_startproc
	pushq	%rbp
	.cfi_def_cfa_offset 16
	.cfi_offset 6, -16
	movq	%rsp, %rbp
	.cfi_def_cfa_register 6
	movl	$.LC0, %edi
	call	puts
	movl	$0, %eax
	popq	%rbp
	.cfi_def_cfa 7, 8
	ret
	.cfi_endproc
.LFE0:
	.size	main, .-main
	.ident	"GCC: (GNU) 12.3.1 20230508 (Red Hat 12.3.1-1)"
	.section	.note.GNU-stack,"",@progbits
```

That's a lot more code! But it is much simpler and far more readable than the long string of `1`s and `0`s that it is representing.

Now look at the initial Python code we started with, which belongs to the third generation of programming languages. The difference in length and complexity is _exactly_ why we're able to do so much more with programming languages, and computers in general, today. It demonstrates what I mean by __layered abstraction__. As programming languages develop, more and more gets delegated to the computer to figure out to make it easier for the human; the challenge is to do this with minimal loss in execution speed.

Don't worry about understanding what is actually going on with the code, especially the assembly code, but just pay attention to the reduction in size and complexity you get from layered abstractions. This is what allows you, the programmer, to make the best use of your time. Exactly how a programming language makes these abstractions to reduce the amount of code __you__ need to write is one of its key distinguishing features.