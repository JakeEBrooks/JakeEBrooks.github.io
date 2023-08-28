---
layout: default
title: "Binary Numbers"
permalink: "/docs/fundamental_concepts/binary_numbers"
parent: Fundamental Concepts
nav_order: 1
---

## Binary Numbers
It is quite remarkable when you sit back and _really_ think about it. The only thing the computer in front of you needs to work is electricity, and yet our entire way of life is built on it. Every aspect of our daily lives only exists because the computer in front of you can work wonders with electricity. Our entire global economy, our governments, our schools and universities, our hospitals and care homes, our banks and shopping centres... I could go on. All of these only exist as they do because the computer in front of you can do some pretty amazing things with one simple thing: electricity. What, in all the world, must happen between the plug socket and the screen to allow this craziness?!

To answer that question, we must start by understanding the machine in front of you. In my view, this fundamentally starts with binary numbers. I'm going to indulge myself in a bit of history here and there, since I think it can be quite useful to know where we come from, to understand where we are. I'll keep it brief when I do, but if history really isn't your thing I apologise in advance.

Our number system is very, _very_ old. We find evidence of numbers, not numbers that we would recognise today but numbers nonetheless, being inscribed onto clay tablets that are thousands of years old. They talk about 'three' of this, or 'five' of that. Understanding quantity is actually a very instinctual thing for humans; being able to instinctively understand the difference between one tiger and chasing you, and two tigers chasing you, came in quite handy at some point I'm sure.

Humans have ten fingers and throughout our short time on this planet we have used our fingers to communicate quantity, at an instinctual level, over all the different language barriers that have developed. Imagine for a moment, you are a trader in ancient [Sumeria](https://en.wikipedia.org/wiki/Sumer) over 4000 years ago. Your client is [Akkadian](https://en.wikipedia.org/wiki/Akkadian_Empire) and speaks only Akkadian, but you do not speak Akkadian! How then, are you supposed to do business with this person? Well, your first _instinct_ would be to hold up a few fingers and point at something to communicate 'a few of these?', and through some negotiation involving lots of waving at each other, you might eventually come to an arrangement, all without speaking the same language.

Is it any wonder then, that our common number system is based on ten unique digits, from ten unique fingers? Today, We use [symbols derived from the ancient Arab world](https://en.wikipedia.org/wiki/Arabic_numerals) to represent these digits in writing. These symbols are, of course, the symbols 0-9 (0 being one finger... just go with it). Any number you can think of can be described using the same ten symbols and following a common set of rules. One rule, for example, is that the number has an additional digit for every power of ten you cross in getting to that number: to represent the quantity of 45 with your fingers, you have to hold up ten fingers ($10^1$) at least once, so the written number must have 2 (1 base + 1 additional) digits.

But there isn't actually anything that ties us to using ten unique symbols as a basis for a number system, just the convenience of being able to easily map them to something the vast majority of humans possess: ten fingers. What if, we were instead born with eight fingers? Our number system would likely use a system of eight fundamental symbols! Or perhaps, through a quirk of evolution, we instead opted to wave an arm around to communicate 'one of something' to our fellow humans. Our number system would use only two unique symbols since we have only two arms! So funnily enough, you can actually begin to understand binary numbers by waving your arms around (just don't let the neighbours catch you practicing...), since binary numbers also use two unique symbols: 0 and 1.

Binary numbers follow very similar rules to regular base-10 numbers, the key difference being that instead of powers of ten being the 'crossing point', it is powers of two. Let's learn to count in binary...

| Base-10    | Base-2 (Binary) |
|:-----------|:----------------|
| 0          | 0               |
| 1          | 1               |

We've ran out of arms! ... actually what I meant to say is that we've now crossed a power of two (2^1), so we're going need an extra binary digit...

| 2          | 10              |
| 3          | 11              |

and now we need another digit since we've crossed another power of two (2^2)...

| 4          | 100             |
| 5          | 101             |
| 6          | 110             |
| 7          | 111             |

... and again for 2^3 ...

| 8          | 1000            |
| 9          | 1001            |

Now watch carefully here, because we're going to do a similar thing for the regular base-10 number, since we're going to cross 10^1...

| 10         | 1010            |
| 11         | 1011            |
| 12         | 1100            |
| 13         | 1101            |

... and so on. The quantity is communicated just as in the normal base-10 rulebook you've been using your whole life, but adding together the necessary powers of two instead. An explicit example:

`13 = 1*2^3 + 1*2^2 + 0*2^1 + 1*2^0`

just like in the base-10 system you instinctively know:

`13 = 1*10^1 + 3*10^0`

And that's binary numbers!

Now you might've seen them written with leading zeros before, like `3 = 0011`. This doesn't have a mathematical meaning beyond what I've just shown above, but it does communicate something else. Before we get to that, let me explain why I've taught you to skillfully wave your arms around.

## Representing information with binary numbers
As we know, computers run on electricity, but it's more accurate to say that computers run on carefully timed bursts of electricity. To make this concrete, imagine a scenario where I have stupidly agreed to be shocked by you, with the aim of you telling me how old you are, all without uttering a single word. We agree to use binary numbers, and every ten seconds I am either painfully electrocuted, or not. If, at the ten second mark, I am electrocuted I know that means you sent a binary `1`. If not, I know you just sent a binary `0`. Say you are thirty years old, and in binary `30 = 11110`. We have agreed to go from left to right in binary, so I am barbarically shocked four times in a row and then spared at the fiftieth second.

Based on the rules we agreed to earlier, I know you just told me you are 30 years old! Fun! To expand on this idea, imagine that we then agree to assign binary numbers to all the letters in the alphabet. For example, we might say that `01100101 = e`. Now we can pass sadistic messages to one another by taking turns in the torture device and sending a sequence of letters back and forth.

Assigning binary numbers to letters is exactly how [ASCII](https://en.wikipedia.org/wiki/ASCII) (American Standard Code for Information Interchange) works, and is the fundamental rulebook that allows you to talk to the computer and vice versa. The letters you press on a keyboard correspond to a specific electric signal that is sent to the computer by the keyboard. The computer, knowing the ASCII rulebook, knows exactly the letter you just pressed based on the number of electric pulses that were sent or not sent in a pre-determined time period.

Now let's return to how binary numbers are written, and why they might have leading zeros. There are a few reasons binary numbers often come in fixed lengths. One is because it is helpful, and more efficient, to know exactly how many electric bursts you may or may not receive in advance. Sort of like an implicit 'end of message'. If the computer is aware you are always sending eight binary digits, it can plan and schedule itself around this rule rather than around every burst of electricity that gets sent. It makes the whole process a lot faster, because the bandwidth between you and the computer is a lot wider. 

The other reason relates to computer memory, and how binary numbers are stored in the various [storage devices](https://en.wikipedia.org/wiki/Data_storage) around today. You have undoubtedly heard of 'bytes' or 'gigabytes' or megabytes'. The 'byte' has emerged has a common binary unit in all matters related to computers, and a 'byte' is simply an eight-digit binary number. For reference:

one __bit__ = __one digit binary number__ (like 0 or 1)\
one __nibble__ = __four digit binary number__ (like 0011 or 1011, no I'm not joking)\
one __byte__ = __eight digit binary number__ (like 11100010)\

Say our computer has a maximum storage capacity of 100 gigabytes. One gigabyte means 1 billion bytes, which in turn means 8 billion bits. We have one hundred gigabytes, so we can store 800 billion binary digits in our computer! It's a literal translation: one-giga-byte(s) = one-billion-bitsx8

Practically speaking, it's not unreasonable to think of a storage device, like a hard drive, as just a really big book. On each page you can only write a certain number of digits (bits) since each digit has a fixed width, so the overall book can only fit a certain amount of information.

In the next section, we'll talk about the components of a computer and how storage devices fit into this structure. Take a break, and then [we'll get stuck in](./binary_logic)