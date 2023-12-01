# Lets Make A CPU - by AmethystDev2713
### Copyright Nov. 30, 2023 AmethystDev2713. All rights reserves, this ebook may not be copied, distributed, or used to make deriative works and similar without a certificate of permission by the copyright holder, AmethystDev2713

## Table of contents

| Section Name                              | What we cover                                                               |
|:-----------------------------------------:|:---------------------------------------------------------------------------:|
| Overview                                  | The basics of computers and CPUs                                            |
| Section 1: Logic Gates                    | Transistors and Logic Gates: The building blocks of CPUs                    |
| Section 2: Areas of a CPU                 | What is the Control Unit, ALU, and Registers?                               |
| Section 3: Intro to binary                | What is binary and how does it work?                                        |
| Section 4: Assembly & The Instruction Set | What is the instruction set and what does it do?                            |

**Note:** This is a very long ebook, and as such it will take a while to finish. What you are reading right now is an incomplete version. Check every so often for updates if you'd like

## Overview

If you're anything like me, you are curious about the computer's inner workings. One of the most powerful and important components is called the Centeral Processing Unit, or CPU. It's basically the brain of the computer. As StoryBots puts it, a computer/CPU is 3 simple steps: Input, Processing, Output.

**Input:** In this step, the CPU retrieves information from a memory source, such as RAM (Random Access Memory), ROM (Read Only Memory), Storage (USB drives/sticks/thumb drives, Hard disks, floppy disks, etc), or direct user input from a device like a keyboard. This process is like a student learning a new concept in school or remembering the answer to a question on a test. In computers, input is generally in one of the two forms: Instructions, which are the most important, or data, such as addresses to access different things in the computer, or simple numbers and letters. Let's go more in depth with these two forms of input

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

![Not Gate Made From A Transistor]("NOT Gate Made From A Transistor")

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

The video by In One Lesson also goes into depth on how each of these use. In short, the control unit is the brain of the CPU, the ALU does math operations, and the Registers are temporary, quick access storage places inside the CPU. Each of these areas are made with logic gates to carry out instructions that the creator wants it to.

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

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; number in decimal ^^^^

2. The same principle applies to larger binary numbers, like 16-Bit Binary Numbers.

The bit at place 2 is set to 1, so one of out factors is 2. Same thing with place 16, so add 16 + 2, and the result of 00010010 converted to decimal is 18. Learning to convert binary to decimal can be helpful when developing your CPU since it's a crucial part of creating your instruction set

### Section 4: Assembly & The Instruction Set

Just like numbers are represented in binary, you can "program" your CPU, in a way, to accept certain combinations of binary bits as an instruction. The 6502 CPU's datasheet, and other CPU's datasheets (basically their manuel, **please** whatever you do, don't look up the Intel manuels. They will horrify and confuse you beyond the capacity of your brain), tell you what of its 50ish instructions are in hexadecimal, which is another numbering system, like binary, used in computing, where each bit has 16 possible combinations instead of 2, like with binary. But we won't get in depth with that since you're better off using binary when making a simple CPU. If you ever become smart enough and design your own 16-Bit, 32-Bit, or even 64-Bit CPU, which would be a SUPER impressive feat, you would rather write a hexadecimal number like 09D7 than a binary number like 0101010100111111, which is obviously very long. Anyways, here are the steps to designing your instruction set:

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

Here is the code explanation: Load the correct number into register A, which is 1001 in binary, or 9 in decimal. Get the user's guess with the IN instruction. Since it saves to register C, compare the user's input (Register A) with the user's guess (Register C). If they are the same (meaning the user has guessed the correct number), skip the "guess again" message and jump to the "Correct! Good Job!" message to tell the user they guessed the correct number. If the 2 numbers are not equal, then the JMPX instruction will be ignored, since the user didn't guess the correct number, and will then show the "guess again" message and jump to the IN instruction to get the user's next guess.
