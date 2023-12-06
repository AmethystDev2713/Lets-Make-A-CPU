# Lets Make A CPU - by AmethystDev2713
### Copyright Nov. 30, 2023 AmethystDev2713. All rights reserves, this ebook may not be copied, distributed, or used to make deriative guides/books/ebooks/newspapers/anything similar without a certificate of permission by the copyright holder, AmethystDev2713

## Table of contents

| Section Name                                         | What we cover                                                                                                         |
|:----------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------:|
| Overview                                             | The basics of computers and CPUs                                                                                      |
| Section 1: Logic Gates                               | Transistors and Logic Gates: The building blocks of CPUs                                                              |
| Section 2: Areas of a CPU                            | What is the Control Unit, ALU, and Registers?                                                                         |
| Section 3: Intro to binary                           | What is binary and how does it work?                                                                                  |
| Section 4: Assembly & The Instruction Set            | What is the instruction set and what does it do?                                                                      |
| Section 5: Constructing our CPU                      | What are the steps to build our CPU?                                                                                  |
| 5.1: Register Loading/Multi Step Instructions        | How do we make a register instruction processor? How do we avoid error when making multi-step instruction processors? |
| 5.2: 3-Step Instructions/Add + Subtract Instructions | How do we make a 3-step instruction processor? How do CPUs add + subtract binary numbers?                             |

**Note:** This is a very long ebook, and as such it will take a while to finish. What you are reading right now is an incomplete version. Check every so often for updates if you'd like

## Overview

If you're anything like me, you are curious about the computer's inner workings. One of the most powerful and important components is called the Centeral Processing Unit, or CPU. It's basically the brain of the computer. As StoryBots puts it, a computer/CPU is 3 simple steps: Input, Processing, Output.

**Input:** In this step, the CPU retrieves information from a memory source, such as RAM (Random Access Memory), ROM (Read Only Memory), Storage (USB drives/sticks/thumb drives, Hard disks, floppy disks, etc), or direct user input from a device like a keyboard. This process is like a student learning a new concept in school or remembering the answer to a question on a test. In computers, input is generally in one of the two forms: Instructions, which are the most important, or data, such as addresses to access different things in the computer, or simply numbers and letters. Let's go more in depth with these two forms of input

- Instructions
    - These are like your parents telling you to do your chores or your teacher telling you what your assignment is and how to do it. Instructions are words (in assembly, we'll talk about how that works later on) like CMP, which stands for Compare, which is used to compare two values, such as if they are equal, not equal, the first is greater than the second, or the first is less than the second.
- Data
    - This is simply information, like an essay. Let's say the CPU is doing a compare instruction, it needs data to compare, otherwise it does nothing or results in an error. Data can be in the form numbers, letters, addresses, etc. For example, if there is an instruction to put text on the screen, the CPU needs to know what to put on the screen, which is the data.

**Processing:** In this step, the CPU does the work it is told to do from input. There are a lot of things that can go on during processing, such as math operations, reading information from storage, etc. Like we discussed above with instructions, processing things like instructions is how the CPU will know what to do.

**Output:** There may not always be output to the user of the computer. Sometimes there is and sometimes there is not. For example, if a person who writes in the language of computers to create what are called programs, a set of instructions to tell the computer what to do without having to be rewritten every time, and is usually saved to storage, more commonly refered to as a programmer, decides to make a calculator program, and the user wants to know what is 35 * 7, the program will output the answer when it is done processing. An example of no output might be a two-step calculation, such as (35 * 7) - 26. In this kind of a calculation, you won't see the answer of 35 * 7 and the subtraction of 26, you will only see the final result, not both numbers. Think of how confused people would be if that was the case if someone made a quadratic formula solver! Numbers upon numbers we would see...

This is the basics of how a CPU works, but if you want to know more, I would highly recommend checking out [this video by In One Lesson on Youtube](https://www.youtube.com/watch?v=cNN_tTXABUA) which goes into deep detail on how a CPU works without using crazy language that the general public may not understand

## Let's get started

### Section 1: Logic Gates

All CPUs at their heart are made up of one thing, the transistor

![Transistor](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/0559d359aa6f8ee89d8a11bc57689e114e27c1d1/Transistor.png "Transistor")

All these marvels of engineering are is simple switches. As you can see above, the Transistor has 3 legs or wires comming out of it, a base, collector, and emitter.

**Base:** If a small amout of power/electricity is applied to this leg, the transistor turns on, and lets any current coming into the collector to flow out of the emitter

**Collector:** This is the transistor's input. If the base is on, but there is no electricity coming from the collector, there will be no output through the emitter

**Emitter:** This is the transistor's output. The only way to get output from a transistor is to have electricity flowing to the base, and the collector. Think of the base as a key, and the collector as the lock, and the emitter like the unlocked door. If there is a key, but no lock to use it on, the door won't open. If there is a lock but no key, the door also won't open. If there is a lock and a key, the door can be unlocked and opened.

While this might seem simple and useless, I'm about to explain why this invention is such a breakthrough, aside from it being it to operate at near the speed of light and being so simple that it can be manufactures to be so small, you need a microscope to see it. Seriously, the millions and even billions of transistors that make up a CPU, are only a few ATOMS wide! Isn't that incredible?

Anyways, the reason why transistors are 98% of the whole CPU, is because their bases, collectors, and emitters can be arranged in certain ways to make what are called "Logic Gates". They perform what are called Boolean operations, whose only two possible inputs and outputs are on and off. This is also explained better in the video by In One Lesson. Here are a few examples: AND, OR, NOT

**AND Gate**

![AND Gate Made From Transistors](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/32e6f8b74aee126594da21240b047f10e3d3fffe/AND%20Gate.png "AND Gate Made From Transistors")

To find out what the 4 possible combinations of inputs from the switches do, we use truth tables, which tell whether a switch is on or off by using a 0 for on and 1 for off

| Switch A | Switch B | Output |
|:--------:|:--------:|:------:|
| 0        | 0        | 0      |
| 1        | 0        | 0      |
| 0        | 1        | 0      |
| 1        | 1        | 1      |

This shows that the AND Gate will not turn on unless both of the switches are one, hence, the name

**OR Gate**

![OR Gate Made From Transistors](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/b62be35fb1ee1d3c8f313a1d8cc9ca5d5b42c69b/Images/OR%20Gate.png "OR Gate Made From Transistors")

In this case, both of the collectors are powered, so when either, or even both of the inputs are powered, there will be an output.

Truth table:
| Switch A | Switch B | Output |
|:--------:|:--------:|:------:|
| 0        | 0        | 0      |
| 1        | 0        | 1      |
| 0        | 1        | 1      |
| 1        | 1        | 1      |

**NOT Gate**

![Not Gate Made From A Transistor](about:blank "NOT Gate Made From A Transistor")

The NOT Gate, also known as an inverter, will invert the input. This means if there is no power, there will be a power output, and if there is a power input, there will be no power output. Here is the truth table (Note: There is only one input)

| Switch | Output |
|:------:|:------:|
| 0      | 1      |
| 1      | 0      |

These basic logic gates are used to form more complicated logic gates, such as the XOR (pronounces Ex-Or), NOR, and NAND. Here are their Truth tables

**XOR:** Exclusive OR, only 1 input can be on for there to be an output

| Switch A | Switch B | Output |
|:--------:|:--------:|:------:|
| 0        | 0        | 0      |
| 1        | 0        | 1      |
| 0        | 1        | 1      |
| 1        | 1        | 0      |

**NOR:** Inverted OR, either or both inputs being on will turn off the gate

| Switch A | Switch B | Output |
|:--------:|:--------:|:------:|
| 0        | 0        | 1      |
| 1        | 0        | 0      |
| 0        | 1        | 0      |
| 1        | 1        | 0      |

**NAND:** Inverted AND, Both inputs must be on for the gate to turn off

| Switch A | Switch B | Output |
|:--------:|:--------:|:------:|
| 0        | 0        | 1      |
| 1        | 0        | 1      |
| 0        | 1        | 1      |
| 1        | 1        | 0      |

These gates, made from transistors, are the building blocks of every CPU. A good online software to start making your own logic boards is [simulator.io](https://simulator.io). I love using this logic gate simulator due to it being easy to learn how to use it (I would highly recommend checking out their [sample circuits](https://simulator.io/samples)). 2 Important notes about simulator.io:

1. Unfortunatly, it's impossible to make private boards only you can see, so if you want to make private boards, I would suggest using [Logigator](https://logigator.com/), which allows you to export your logic boards to project files you can save and use later, therefore making your work private
2. You can't use individual transistors in this simulator, only the logic gates and other integrated circuits (ICs) provided

### Section 2: Areas of a CPU

With out new knowledge of transistors and logic gates, we can talk about the 3 basic areas of a CPU, the Control Unit, ALU, and Registers

**Control Unit:** This is the brain of the CPU, which tells the ALU and Registers to do. It's job is to process most instructions, control registers, and work with the ALU. The control unit can process all instructions except for arthematic and comparision instructions. Those two types of instructions are processed by the ALU.

**ALU (Arthematic Logic Unit):** This area of the CPU basically does math and inequality instructions

**Registers:** This are little storage spaces which store a byte or a few bytes of data that the CPU needs to access repetitivly and quickly

The video by In One Lesson also goes into depth on how each of these are used in a CPU. In short, the control unit is the brain of the CPU, the ALU does math operations, and the Registers are temporary, quick access storage places inside the CPU. Each of these areas are made with logic gates to carry out instructions that the creator wants it to.

### Section 3: An intro to Binary

Before you run away from the computer screaming upon hearing "assembly", we won't be using x86 or 64-Bit assembly, they're WAAY to complicated for our purposes. Instead, we will be using the very famous 6502 8-Bit microprocessor (pronounced six-five-oh-two or sixtey five-oh-two, I personally prefer the first pronounciation), made by MOS Technology, and used in famous computers of its era, such as the Apple II and Commodore 64, as our example CPU for this section.

Computers work by using a number system called Binary. It's a system where values/data/instructions are represented in 1s and 0s. Binary is the language of computers, and in the case of the 6502 CPU, being an 8-Bit CPU, it's binary system uses 8 places where there can be a 1 or 0, which are called bits. By today's standards, 8 bits is equal to 1 byte. Here is an example of an 8-Bit number: 01011110. For demonstration purposes, let's say that 01011110 is a number. How do we know what it is in decimal (the number system us humans use, which is 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, etc) ? People have come up with a smart strategy to convert binary into decimal, but if you don't want to do the calculations manually, which is perfectly fine, you can use an online calculator. If you would like to do the calculations by hand, here is a guide:

1. An 8-Bit Binary can represent values from 0 to 255. For Example, 00000001 is one, 00000010 is 2, 00000011 is 3, and so on. Here's the key concept: 2-Bit Binary can represent numbers 0 - 3, so the first bit, which is the rightmost bit, represents 1, and the left most bit represents 2. With 3-Bit, you can see values 0-7, so from **Right to left**, each bit represents 1, 2, and 4. For each bit from right to left, the value it represents is double the last. Here's a diagram to convert a random binary number to decimal

| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|128| 64| 32| 16| 8 | 4 | 2 | 1 |

What this is showing is if the bit at a given place is 1, it takes the value underneath it. For example:

| 0 | 0 | 0 | 1 | 0 | 0 | 1 | 0 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|128| 64| 32| 16| 8 | 4 | 2 | 1 |
|.  |.  |.  | 16|.  |.  | 2 |.  |
|.  |.  |add|---|---|---|---|---|
|.  |.  |.  |.  |.  |.  | 18|.  |

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;number in decimal ^^^^

2. The same principle applies to larger binary numbers, like 16-Bit Binary Numbers.

The bit at place 2 is set to 1, so one of out factors is 2. Same thing with place 16, so add 16 + 2, and the result of 00010010 converted to decimal is 18. Learning to convert binary to decimal can be helpful when developing your CPU since it's a crucial part of creating your instruction set

### Section 4: Assembly & The Instruction Set

Just like numbers are represented in binary, you can "program" your CPU, so to speak, to accept certain combinations of binary bits as an instruction. Obviously, it's much harder to remember a binary number than an assembly instruction. Assembly is basically the CPU's language written in a form easily understantable by humans. The 6502 CPU's datasheet, and other CPU's datasheets (basically their manuel, **please** whatever you do, don't look up the Intel manuels. They will horrify and confuse you beyond the capacity of your brain), tell you what of its 50ish instructions are in hexadecimal, which is another numbering system, like binary, used in computing, where each bit has 16 possible combinations instead of 2, like with binary. But we won't get in depth with that since you're better off using binary when making a simple CPU. If you ever become smart enough and design your own 16-Bit, 32-Bit, or even 64-Bit CPU, which would be a SUPER impressive feat, you would rather write a hexadecimal number like 09D7 than a binary number like 0101010100111111, which is obviously very long. Anyways, here are the steps to designing your instruction set:

- Planning.
   - What is your CPU going to be like? Is it going to be super simple (like my [3-Bit CPU](https://simulator.io/board/C2geCb4c2j), if you can even call it a CPU) and only adds and subtracts numbers? Is it going to be designed for use in mechanical contraptions, like a loom machine? Maybe for robots? Perhaps for a computer, which is the most common use for a CPU. Depending on the use, you can conclude what kind of instructions it should have
   - What will its binary range be? Will it be 4-Bit (I would recommend this as your minimum if you are making a CPU to actually do something useful) like the world's first CPU, the Intel 4004? 8-Bit, like the 6502 or Z80? 16-bit, like the 65816 or Motorola 68000 series? The more funtionality you want, the higher your binary range should be.
- Drafting
   - Your CPU should, at minimum, have the following types of fundamental instructions:
      - Load instructions, which can write values to registers or read data from RAM or ROM and save it to a register
      - Compare instructions, which are basically inequality operations. These can be used in things as simple as a number guessing game to an OS (Operating System, such as Windows, Macintosh/Mac, Linux, etc) for your CPU
      - Input Instructions, which can take the user's input for something like a number guessing game
      - Output instructions, which can be as simple as turning on or off a set of LEDs or as complicated as outputting what's going on in a video game to the screen
   - Aside from those 4, you can decide whatever else you want your computer to do! It's going to be your design, after all
   - Create an instruction set table, such as this one:

| Instruction name | Binary form | Usage                                                                                      |
|:-----------------|:-----------:|:-------------------------------------------------------------------------------------------|
| LDA              | 0001        | Load a byte of data into register A                                                        |
| LDB              | 0010        | Load a byte of data into register B                                                        |
| LDC              | 0011        | Load a byte of data into register C                                                        |
| CMPE             | 0100        | Check if the next 2 binary numbers following are equal to each other                       |
| CMPN             | 0101        | Check if the next 2 binary numbers following are not equal to each other                   |
| CMPG             | 0100        | Check if the next binary number following is greater than the next binary number           |
| CMPL             | 0101        | Check if the next binary number following is less than the next binary number              |
| IN               | 0110        | Get Input from the input device, saves to register C                                       |
| OUT              | 0111        | Send output to an output device                                                            |
| ADD              | 1000        | Adds the next 2 binary numbers, saves to register C                                        |
| SUB              | 1001        | Subtracts the next 2 binary numbers, saves to register C                                   |
| JMP              | 1010        | Jump to a line in code file                                                                |
| JMPX             | 1011        | Jump to a line in code file if the previous comparision resulted in "true" as its result   |
| RGA              | 1100        | Keyword: Used to use the value of register A with other instructions                       |
| RGB              | 1101        | Keyword: Used to use the value of register B with other instructions                       |
| RGC              | 1110        | Keyword: Used to use the value of register C with other instructions                       |

The left most column is the instruction in assembly, which is a special class of programming language called machine language, or machine code, because these instructions carry out operations exactly like the CPU does and grant the user full access to the CPU. This is generally only used by experienced computer workers, but in our case, where we are making our own CPU and assembly code for it, we don't need a professional or highly experienced user to do the work, since it's your very own variation of assembly, designed for your CPU. The middle column shows the instruction in binary, which is how your CPU will read it, and the right most column, well, explains it. As simple as these seem, you can already make simple programs, and maybe even find uses nobody ever knew about when using mutiple different instructions together! Here's a code example for a number guessing game using the assembly table above:

1. `LDA 1001`
2. `IN`
3. `CMPE RGA RGC`
4. `JMPX 7`
5. `OUT Guess again`
6. `JMPX 2`
7. `OUT Correct! Good Job!`

Here is the code explanation: Load the correct number into register A, which is 1001 in binary, or 9 in decimal. Get the user's guess with the IN instruction. Since it saves to register C, compare the user's input (Register A) with the user's guess (Register C). If they are the same (meaning the user has guessed the correct number), skip the "guess again" message and jump to the "Correct! Good Job!" message to tell the user they guessed the correct number. If the 2 numbers are not equal, then the JMPX instruction will be ignored, since the user didn't guess the correct number, and will then show the "guess again" message and jump to the IN instruction to get the user's next guess. Of course, CPU's only understand 1s and 0s, so you will need to do a process called "interpreting" where you convert (or a program you made converts) the assembly code into 1s and 0s based off of your table. After you have 1s and 0s, your CPU will now be able to read your code! The only problem in this specific example is we are unable to interpret text into binary, since we have too few bits, as for with numbers, you can represent them as binary numbers 0000 - 1111, since this is a 4-Bit CPU example. In order for it to be actually interpreted, if you want, would be to replace "guess again" with 0 to indicate that the wrong number was guessed, and "Correct! Good Job!" with 1 to indicate that the correct number was guessed. Like I've mentioned before, if you want to make your CPU do more, you will have to increase your binary range to give more possible combinations of binary, representing more and more functions for the CPU to carry out.

### Section 5: Constructing our CPU

This is when logic gates come in. You can arrange all types of logic gates to make them do different functions. If you examine my CPU, you will see a logic part for each of the 4 instructions. This is generally how I construct CPUs:

1. Create a part to check if a certain binary combination has been inputted. This can usually be done with an AND gate with as many inputs as the binary range is. For example, If you look at the first instruction processor on my example CPU, you can see some of the inputs are inverted to ensure that only a very specific combination of binary will allow the instruction to start processing. Another important part of this step is to create a locking mechanism, so that the CPU doesn't get confused on which bytes are for each instruction. Here's a diagram on Simulator.io:

![Example 1](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/ac62c398d547b5c68f0f59da2c91745f5faa5528/Images/Instruction%20Locker%20-%201.png "Example 1")
![Example 2](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/e6705f49d7c0250421aceaa68b8912839c262321/Images/Instruction%20Locker%20-%202.png "Example 2")
![Example 3](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/15ba8e410ca47981865b401a35e422d562d0758b/Images/Instruction%20Locker%20-%203.png "Example 3")

In the examples above, you can see that only the specific binary combination to activate an instruction is inputted, only that instruction processor (the group of logic gates that do the instruction you want) will turn on, and it will lock the others to prevent them from accidentally turning on, until that instruction processor is done processing. For demonstration purposes, each "programmed" instruction with logic gates will turn on an LED to indicate that they are active and lock the other one. In a real CPU, in the place of the LEDs would be more logic gates to do whatever the designer wants the CPU to do.

A more efficient way to do this is by creating a locking mechanism on the input wires themselves, like so:

![Example 4.1](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/63301493128e56ba87f931da5747314d21c1dd71/Images/Locker%20v2%20-%201.png "Example 4.1")
![Example 4.2](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/366036111810a3c14afd44bdee1d90eff294b841/Images/Locker%20v2%20-%202.png "Example 4.2")

In this example, when the binary code for an instruction is inputted, the instruction locks the data input to prevent it from going beyong the instruction processor by using 4 AND gates with one inverted input (the circle on one of its inputs represents a NOT gate). When the instruction is activated, it turns on the inverted inputs, which actually turns off that input since it's inverted. That way, data can't go through the locker. This makes it easier to prevent accidentally activating other instructions rather than wires going all over the place to lock other instructions.

2. Set up (a lot) of logic gates to do what I want the CPU to do, whether it's a register, ALU, output functions, etc.
3. Test the CPU. Just like programming in a language like C++ (my personal favorite), you have to test your code for bugs. Similarly, you have to test your logic circuit (set of logic gates which work together as a unit to perform a task) to make sure it's working the way it should be.

You can think of the process as this: Plan (this is what section 4 was about), Build, and Test, just as if you were building a robot, RC Car/Airplane, making a Lego set from your imagination, etc.

#### 5.1 Register Loading/Multi Step Instructions

Let's find out how to make a multi-step instruction that will lock the other instructions as needed until it's over. An example of a multi-step instruction is loading a value into a register. Let's break down how to make a register loading instruction.

This is a register using RS Latches (Reset-Set Latches) which will hold one state depending on whether the reset or set input is powered, even if it's temporary.

![Register Mechanism](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/0313285452e68f102b16071e7b28f23171c2d7dd/Images/Register%20Loading%20Mechanism.gif "Register Mechanism")

Of course, this isn't the full picture, it's just a simple demonstration on how a register work. To combine the activation and register loading, we need a logic circuit which will lock the other instruction processors until we are ready to move on. D-Latches/Flip Flops are a really nice circuit which can do that. Unfortunatly, they are sort of a complicated concept. You can check out simulator.io's D-Latch Sample Circuit to see it in action. Their Diode Matrix/Traffic Light Sample Circuit will be the best thing to look at in order to understand D-Latch counters. A counter is a circuit which will count up, in the sense of a program counter. In our case, it will tick twice before giving an output, signaling the end of out two-step instruction. For a three step instruction, you would make a circuit using 2 D-Latches and an AND gate.

![3-Step Counter](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/716e1df2bdd5bc489c1467facbddf73f2902e885/Images/3-Step%20Counter.gif "3-Step Counter")

Just to note, a 4th pulse will be required to reset the counter.

Surprisingly, D-Latch Circuits don't work in Logigator, so when I checked out their sample circuits to see how to make a counter with their simulator, I was very, very shocked to see that you can just use half adders, which are a circuit which can add 2, 1-Bit binary numbers. To make a counter using them, simply replace the D-Latches with Half-Adders and change the wiring a bit

![3-Step Counter Using Half Adders](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/64ecfaff2a5dc91221b93574346e0607ac36f22e/Images/3-Step%20Counter%20With%20Half%20Adders.gif "3-Step Counter Using Half Adders")

This design also requires a 4th pulse to reset the counter.

Fortunatly, this design works in both Logigator AND Simulator.io (pun not intended), but there is the problem of how fast the counter can switch between outputting different binary numbers, since there is a slight delay when switching between numbers, meaning it takes time for each bit to turn on and off, so a counter could end up displpaying a completly off-track binary number before displaying the correct one, so be careful when making counter. Rest assured that it is possible to create a set of logic gates that will remove the time delay from the output

Since instructions like these take multiple inputs/steps, we need to make sure we aren't accidentally triggering other instruction processors while one instruction is still running.

Now, we have 3 mechanisms, the counter, register, and the locker. But how does the register get input?

First, the register needs to be reset on each instruction so the previous value is cleared and the new value/data can be saved. To do this, we add wires going to the data input wires, and another locker to make sure we are only saving data when the instruction is activated. To prevent the bit which activated the instruction from being saved, we use an AND gate with an inverted input which will allow data saving once there is no data coming in. This is where the entire instruction processor comes together

![Full Register Loading Mechanism](https://github.com/AmethystDev2713/Lets-Make-A-CPU/blob/f9a83c461a50afb5aaf9266b3f49e803093154ee/Images/Full%20Register%20Loading%20Mechanism.png "Full Register Loading Mechanism")

![Animation of full register loading mechanism](about:blank "Animation of full register loading mechanism")

I know, it's absolute madness, so lets break it down.

We start with an AND Gate which checks to see if the binary code to activate the instruction (0001) is being inputted. If so, activate the instruction processor (All the logic gates to the right of it)

![Binary checker](about:blank "Binary checker")

Then, a RS latch acts like a flag, which is somewhat like a traffic light, saying "It's time for a second input!", and also turns on the D-Latch/counter's clock wire. The counter will not give an output until it's clock wire turns off (the clock wire is represented by a (>) symbol). In the mean time, once the first input is gone, the register lock will turn on, unlocking the wires to save a binary number to the register

![Register locker + register](about:blank "Register locker + register")

This AND Gate with an inverted input will check if the first input, which activated the instruction processor, is gone. Only then will it unlock the register lock.

![Buffering AND Gate](about:blank "Buffering AND Gate")

The instruction processor needs a way to tell when input is done. The section of logic gates here does exactly that

![Instruction Done Checker](about:blank "Instruction Done Checker")

The output wire of the Instruction Done Checker Runs to the Locker for the counter. When It's locked, the counter will output 1, or it will turn on, which resets the flag to signal the instruction is done. The Checker's output wire also runs to some logic gates which reset the counter, so future instructions don't confuse that instruction processor into thinking its instruction is still running.

![1st Instruction Resetter](about:blank "1st Instruction Resetter")
![2nd Instruction Resetter](about:blank "2nd Instruction Resetter")

Hopefully with that explanation, the register loading mechanism makes more sense. Whether the instruction is 2-step or 4-step (like a register loading mechanism or a compare instruction, which might be like: Compare [operation] [value1] [value2]), an instruction processor follows these basic steps: Activation, processing, step counting, reset the instruction processor.

#### 5.2: 3-Step Instructions/Add + Subtract Instructions
