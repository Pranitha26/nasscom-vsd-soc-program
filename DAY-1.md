# FUNDAMENTALS OF CHIP DESIGN

<img width="445" alt="image" src="https://github.com/user-attachments/assets/deea4487-1d92-4470-8f14-519e1189681c" />

This is an Arduino board and the encircled part is the chip or processor


<img width="804" alt="image" src="https://github.com/user-attachments/assets/de0f6683-ef6a-4090-9abb-830ad38bbd75" />

This is the board in the form of a block diagram. It is the processor or SoC is the chip, connected to all the interfaces of the board


<img width="818" alt="image" src="https://github.com/user-attachments/assets/917dc4aa-f561-47f3-b3c5-aff865e0d4c5" />

This is called a ***PACKAGE*** 

The Arduino board drives the pin locations of this package.

<img width="493" alt="image" src="https://github.com/user-attachments/assets/4bdfced8-71e7-4360-8b17-e36cabae2501" />

The chip lies somewhere in the middle of the package and is connected in this way to pins. This transfers all the signals from the outer world to the interior of the chip

## COMPONENTS OF THE CHIP



<img width="669" alt="image" src="https://github.com/user-attachments/assets/d80f4734-a20b-4923-a7a9-5e1b10738e75" />

***PADS***: Information flows in and out of the chip through the Pads. They can be thought of as gates to a place; we must pass through a gate to reach it.

***CORE***: The unit where the  digital logic fed into the chip, like the logic gates such as, AND, OR, NOR, etc, resides.

***DIE***: This is the size of the entire chip

<img width="475" alt="image" src="https://github.com/user-attachments/assets/33744dec-4fc1-4101-ae2c-5c98d29013a9" />

The ***Core*** of the chip consists of the RISCV5 SoC, SRAM, PLL, dac, etc. 


The components of the core are called ***FOUNDRY IPs***. They are factories with various machines, where the chips get manufactured.

***IPs***: or Intellectual Properties require some amount of intelligence to build
***MACROS***: are pure digital logic

<img width="798" alt="image" src="https://github.com/user-attachments/assets/c06e80d0-f36a-4cfe-98b3-3d9f95c19752" />


***RISC-V ISA(INSTRUCTION SET ARCHIETECTURE)***


They are methods through which we can communicate with computers, i.e, it is the language of computers
If a C Program has to run on a chip's interior, a certain flow must be followed.
First, the C Program is compiled into its Assembly-Level Program; this is then converted into the Machine-Language Program, i.e, Binary Language which is understood by the hardware of the computer(0 and 1).
Finally, these bits get executed in this layout and the desired output is generated.

<img width="960" alt="image" src="https://github.com/user-attachments/assets/c871d018-f0de-4303-abd0-635b6ba2e53f" />


<img width="981" alt="image" src="https://github.com/user-attachments/assets/07ca5844-a6fb-4ccd-a165-b8622b0c59db" />


<img width="275" alt="image" src="https://github.com/user-attachments/assets/3b7a69b2-534b-4382-bdea-87b1e777b62c" />

Some common apps used by use on an everyday basis.

<img width="352" alt="image" src="https://github.com/user-attachments/assets/68b444eb-e0ae-4179-9c77-1576f4c4c116" />

On our systems, this is how the hardware of these apps look like, i.e, this is the representation of the chip

But, how do the chips become these apps??

To answer that, there is a step by step process

<img width="993" alt="image" src="https://github.com/user-attachments/assets/dd1fc0fc-85c3-43b4-9d0f-b869141c82c3" />

First, these apps enter into blocks to system softwares, which converts the apps into binary language. 

<img width="360" alt="image" src="https://github.com/user-attachments/assets/ce188fe3-3600-4752-816f-24281f88779d" />

The major components/layers of the system software are shown, the OS, compiler, and assembler

Functions of the components:
***OS***: The main job of the OS is to convert the app into its respective assembly language and then to the binary language program.
***Compiler***: takes up the output of the OS which is in the form of C, C++, Java, etc, and converts them into many instructions. 
These instructions belong to the hardware. For instance, if the hardware is IntelX89, the instructions belong to IntelX89.
They are what the .exe file consists of. The ISA as mentioned earlier is nothing but these instructions, which tell us about the system and what it runs on. 
***Assembler***: It converts the instructions into the binary language, which is then fed into the hardware, which performs tasks accordingly.

<img width="979" alt="image" src="https://github.com/user-attachments/assets/3c1af915-fd63-4112-84cc-a5ec9c6b3fa4" />


<img width="973" alt="image" src="https://github.com/user-attachments/assets/07b48e80-6062-45f4-9a5f-0e3379563b0d" />

Let's take the example of a stopwatch. The above image shows the entire work behind the scenes when the app runs
The compiler input of the C Language becomes instructions which are converted into binary by the assembler and then fed into the chip layout.

<img width="994" alt="image" src="https://github.com/user-attachments/assets/f52fb632-2ee4-4964-9ab2-289a636ce386" />

There is an abstract interface between the assembler and the hardware. The binary or the assembler's output passes through implementations
We start by acquiring the specifications from the instructions set. Then, we use RTl to create a hardware description, which is synthesized into a gate level. Finally, we convert this into its respective layout based on the hardware.

There are parts of this course:
<img width="975" alt="image" src="https://github.com/user-attachments/assets/a5a7904f-2bbb-4642-a1aa-af00a8cd9102" />

***DIGITAL ASIC DESIGN***
<img width="978" alt="image" src="https://github.com/user-attachments/assets/f10d957c-ca7d-4e9a-b148-0dce296e5fb7" />

RTL IPs: Hardware 


## DAY 1 Tasks
Calculate the flop ratio

-> Run picorv32a synthesis using openLANE and get the desired output
-> To calculate flip flop ratio:
```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```

```math
Percentage\ of\ DFF's = Flop\ Ratio * 100
```



![image](https://github.com/user-attachments/assets/85f14300-cb85-425d-a930-7efa6a422199)
![image](https://github.com/user-attachments/assets/d645a81b-d444-4fdf-8931-ee42f00cd600)
![image](https://github.com/user-attachments/assets/5375f0db-7679-4356-b023-9d6649659bc2)

#### To calculate the flop ratio:
![image](https://github.com/user-attachments/assets/9689e750-ccc7-4f9a-989c-c8f663658d55)

The highlighted part is the number of D Flops

![image](https://github.com/user-attachments/assets/97fd164c-02c7-46bf-b3bf-7a2a7479bac6)

The highlighted part is the number of cells

Now, 

```math
Flop\ Ratio = \frac{1613}{14876} = 0.108429685
```
```math
Percentage\ of\ DFF's = 0.108429685 * 100 10.84296854\ \%
```

