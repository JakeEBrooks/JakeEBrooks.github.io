---
layout: default
title: "Binary Numbers"
permalink: "/docs/fundamental_concepts/binary_numbers"
parent: Fundamental Concepts
nav_order: 1
---

## Binary Numbers
I'm going to indulge myself in a bit of history here and there, since I think it can be quite useful to know where we come from, to understand where we are. I'll keep it brief when I do, but if history really isn't your thing I apologise in advance.

Our number system is very, very old. We find evidence of numbers being inscribed onto clay tablets that are thousands of years old. They talk about 'three' of this, or 'five' of that. The idea of counting 'three' of this or 'five' of that comes from the digits on our hand. Humans have ten fingers, and throughout our short time on this planet we have used our fingers to communicate quantity over any language barrier. Think about it, you are a trader in ancient Sumeria over 5000 years ago. Your client is Akkadian and speaks only Akkadian, but you do not speak Akkadian. How then, are you supposed to do business with this person? Well, you can hold up five fingers and point at something to communicate 'five of this', and through some negotiation involving lots of waving at each other, you can eventually come to an arrangement.

Is it any wonder then, that our common number system is based on ten unique digits? Today, We use symbols derived from the ancient Arab world to represent the action of 'holding up our fingers' in writing. These symbols are, of course, the symbols 0-9. Any number you can think of can be described using the same ten symbols and following a common set of rules. One rule is that the number has an additional digit for every power of ten you cross in getting to that number: to represent the quantity of 45 'fingers' you have to hold up ten fingers ($10^1$) at least once, so the number must have 2 (1 base + 1 additional) digits.

But there isn't actually anything that ties us to using ten unique symbols as a basis for a number system, just the convenience of being able to easily map them to something the vast majority of humans possess: ten fingers. What if, we were instead born with eight fingers? Well, our number system would likely use a system of eight fundamental symbols. Or perhaps, through a quirk of evolution, we instead opted to hold up our arms to indicate quantity to our fellow humans. Well, then our number system would use only two unique symbols since we have only two arms. So funnily enough, you can actually begin to understand binary numbers by waving your arms around (just don't let the neighbours catch you practicing...), since binary numbers also use two unique symbols: 0 and 1.

Binary numbers follow very similar rules to regular base-10 numbers, the key difference being that instead of powers of ten being the 'crossing point', it is powers of two. Let's see some examples, on the left I'll give the base-10 number, and on the right I'll give the binary (base-2) number:

0 = 0
1 = 1

We've ran out of arms! ... actually what I meant to say is that we've now crossed a power of two (2^1), so we need an extra binary digit...

2 = 10
3 = 11

and now another digit since we've crossed another power of two (2^2)...

4 = 100
5 = 101
6 = 110
7 = 111

... and again ...

8 = 1000
9 = 1001

Now note that we're going to use the same rule in the base-10 rulebook for the base-10 number...

10 = 1010
11 = 1011
12 = 1100

... and so on. The quantity is communicated by adding together the necessary powers of two. In full:

13 = 1*2^3 + 1*2^2 + 0*2^1 + 1*2^0

just like in the base-10 system:

13 = 1*10^1 + 3*10^0

 You've probably seen binary numbers written with leading zeros before, like 3 = 0011. This doesn't have a mathematical meaning beyond what I've just shown above, but it does communicate something else. Before we get to that, let me explain why I've taught you to wave your arms around.

## Representing information with binary numbers
As we know, computers run on electricity, but it's more accurate to say that computers run on carefully timed bursts of electricity. To make this concrete, imagine a scenario where I have stupidly agreed to be shocked by you, with the aim of you telling me how old you are, all without uttering a single word. We agree to use binary numbers, and every ten seconds I am either painfully electrocuted, or I am spared. If, at the ten second mark, I am electrocuted I know that means you sent a binary "1". If I am instead spared, I know you just sent a binary "0". Say you are 30 years old, and in binary 30 = 11110. We have agreed to go from left to right in binary, so I am barbarically shocked four times in a row only to be spared at the fiftieth second. Based on the rules we agreed to earlier, I know you just told me you are 30 years old! Fun! To expand on this idea, imagine that we then agree to assign numbers to certain alphabetical letters. Now we can pass sadistic messsages to one another by taking turns in the torture device and sending a sequence of letters back and forth.

Assigning binary numbers to letters is exactly how ASCII (American Standard Code for Information Interchange, google "ascii table") works, and is how you talk to the computer and vice versa. The letters you press on a keyboard correspond to a specific electric signal that is sent to the computer by the keyboard. The computer, knowing the ASCII rulebook, knows exactly the letter you just pressed.

Now let's return to how binary numbers are written. There are a few reasons binary numbers often come in fixed lengths. One is because it is helpful, and more efficient, to know exactly how many electric bursts you may or may not recieve in advance. Sort of like an implicit 'end of message'. If the computer is aware you are always sending eight digits, it can plan and schedule itself around this rule rather than constantly waiting for an end of message signal after every burst of electricity that gets sent. The other reason relates to computer memory. You have undoubtedly heard of 'bytes' or 'gigabytes' or megabytes'. The 'byte' has emerged has a common binary unit in all matters related to computers, and a 'byte' is simply an eight-digit binary number. For reference:

one bit = one digit binary number (like 0 or 1)
one nibble = four digit binary number (like 0011 or 1011)
one byte = eight digit binary number (like 11100010)

Say our computer has a maximum storage capacity of 100 gigabytes. One gigabyte means 1 billion bytes, which in turn means 8 billion bits. We have one hundred gigabytes, so we can store 800 billion binary digits in our computer! It's not unreasonable to think of a storage device, like a hard drive, as just a big book. On each page you can only fit a certain number of bytes, so the overall book can only fit a certain amount of information. In the next section, we'll talk about the components of a computer and how storage devices fit into this structure.