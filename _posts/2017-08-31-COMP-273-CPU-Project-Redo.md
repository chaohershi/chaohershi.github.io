---
title: COMP 273 CPU Project Redo
---

![CPU](/images/CPU%20Main.gif)

## What is it?

A classic CPU design, stimulated on [Logisim](http://www.cburch.com/logisim/). Last semester, I took the course COMP 273 Introduction to Computer Systems. It was an interesting course that would “remove all fantasies you have about computers…”. The final project was to build a toy CPU and write a piece of machine code that performs multiplications on that CPU. And thanks to my teammates Robert and Jingxian, our CPU got 20.5/20 points! Later, I redid the whole project on June.

![Final project](/images/CPU%20Prototype.png)
*Final project*

## Why redo?

- Though the grade was high, there’s space for improvement.

- I am a little obsessive about neatness.

- For the final project, I only worked on RAM, part of CU, and multiplication circuit. I would like to try out the rest as well.

- To enjoy the joy of design.

![Project redone](/images/CPU.png)
*Project redone*

## What’s new?

Fixes:

- No more buggy wires.

- No delay issue.

- First byte of RAM no longer inaccessible.

New features:

- Clearer layout on all level of circuits.

- CU now let each instruction has its own counter. No more wasted ticks.

- All registers united to the same word size of 8 bits. Expandability improved.

- When ticks enabled (system starts), the process of loading ROM to RAM is now fully automatic.

- Natural way of input. The inputting of value to register and the starting of computation is now automatic.

- Build in automatic reset feature. The CPU will be ready for the next task without any reconfigurations.

Overall, the philosophy of my design is to make the CPU more concise, expandable, and automated.

## Difficulty met

[Gate delay issue](http://www.cburch.com/logisim/docs/2.6.0/en/guide/prop/delays.html)

## My attemps to solve it

![](/images/CPU%20CU%20v1.0.png)
![](/images/CPU%20CU%20v1.1.png)
![](/images/CPU%20CU%20v2.0.png)
![](/images/CPU%20CU%20v2.0%20with%20comments.png)
![](/images/CPU%20CU%20v3.0.png)

Two suggestions:

- Understand the cause of delay issue

- Make the design as simple as possible

## Other thoughts

Though this project is more about the circuit design, during the development, two software development methodologies were strictly followed. They are:

- [Modular programming](https://en.wikipedia.org/wiki/Modular_programming)

- [Iterative and incremental development](https://en.wikipedia.org/wiki/Iterative_and_incremental_development)

And they greatly facilitated the overall development process. These two design techniques are just fundamental yet powerful. Great guidelines to follow.

![](/images/CPU%20Proto%201.png)
![](/images/CPU%20Proto%202.png)
![](/images/CPU%20Proto%203.png)
![](/images/CPU%20Proto%204.png)
![](/images/CPU%20Proto%205.png)
![](/images/CPU%20Proto%206.png)

## Pics

![](/images/CPU%20Main%20Labeled.png)
![](/images/CPU%20Classical%20CPU%20Design.png)
![All components](/images/CPU%20&%20Components.png)
*All components*

## Gifs

![CPU Demo, running at tick frequency 4.1KHz](/images/CPU%20Demo.gif)
*CPU Demo, running at tick frequency 4.1KHz*

![Loading ROM to RAM, tick frequency 32Hz](/images/CPU%20Load%20ROM%20to%20RAM.gif)
*Loading ROM to RAM, tick frequency 32Hz*

![ALU, tick frequency 32Hz](/images/CPU%20ALU.gif)
*ALU, tick frequency 32Hz*

![8B RAM, tick frequency 32Hz](/images/CPU%20RAM.gif)
*8B RAM, tick frequency 32Hz*

![CU, tick frequency 32Hz](/images/CPU%20CU.gif)
*CU, tick frequency 32Hz*

## Credits

Once again, thanks to my teammates Robert and Jingxian. They did a ton of work on the final project, and brought up some brilliant designs. Without the proto design, this redesign won’t go far.
