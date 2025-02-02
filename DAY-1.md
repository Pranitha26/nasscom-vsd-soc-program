# DAY-1: FUNDAMENTALS OF CHIP DESIGN
## How to talk to computers
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


### RISC-V ISA(INSTRUCTION SET ARCHIETECTURE)


They are methods through which we can communicate with computers, i.e, it is the language of computers
If a C Program has to run on a chip's interior, a certain flow must be followed.
First, the C Program is compiled into its Assembly-Level Program; this is then converted into the Machine-Language Program, i.e., Binary Language which is understood by the hardware of the computer(0 and 1).
Finally, these bits get executed in this layout and the desired output is generated.

<img width="960" alt="image" src="https://github.com/user-attachments/assets/c871d018-f0de-4303-abd0-635b6ba2e53f" />


<img width="981" alt="image" src="https://github.com/user-attachments/assets/07ca5844-a6fb-4ccd-a165-b8622b0c59db" />


<img width="275" alt="image" src="https://github.com/user-attachments/assets/3b7a69b2-534b-4382-bdea-87b1e777b62c" />

Some common apps are used by use on an everyday basis.

<img width="352" alt="image" src="https://github.com/user-attachments/assets/68b444eb-e0ae-4179-9c77-1576f4c4c116" />

On our systems, this is how the hardware of these apps looks like, i.e, this is the representation of the chip

But, how do the chips become these apps??

To answer that, there is a step-by-step process

<img width="993" alt="image" src="https://github.com/user-attachments/assets/dd1fc0fc-85c3-43b4-9d0f-b869141c82c3" />

First, these apps enter into blocks to system software, which converts the apps into binary language. 

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

### DIGITAL ASIC DESIGN
<img width="978" alt="image" src="https://github.com/user-attachments/assets/f10d957c-ca7d-4e9a-b148-0dce296e5fb7" />

***RTL IPs***: Hardware description language, registers transfer level models of the functions to be implemented including the RTL of whole use IPs.
***EDA***: Electronic Design Automation, is the CAD tools required to design the circuit, etc 
***PDK Data***: Process design kit

Until 1979, the design & fabrication of the grid circuits were tightly coupled & by only a few companies like TI, Intel, etc.
In 1979, John Conway and Carver Mead proposed separating design from fabrication by releasing Lambda-based design rules. They then published the first VLSI(very large-scale integration) book, Introduction to VLSI Systems. This book gave rise to VLSI education and Structure Design Methodology, which laid the basics of modern ISE design practices. 
After that, many fabric-only companies like ***Pure Play*** and design-only companies like Fabless started to emerge 
***PDK is the interface between the user and Fab, a set of files.***
PDK include Process Design Tools, Design Structured cell libraries, IO libraries, etc. Hence, the PDK has a lot of information distributed under Non-Disclosure Agreements(NDA) making it inaccessible to the public.
In 2020, Google collaborated with Skywater to open-source the PDK for the 130nm Skywater processor, leading to the release of the first ever open-source PDK

![image](https://github.com/user-attachments/assets/34cab4b3-db2a-411e-a0d6-7fc7aeac0255)

#### ASIC Flow Objective
ASIC is a complex process involving numerous steps and technology
To convert RTL to GDSII(Automated PnR and/or Physical Implementation)
GDSII is a binary file format used to exchange information about integrated circuits (ICs). It's the industry standard for Electronic Design Automation (EDA) data exchange.
Steps of RTL to GDSII flow

![image](https://github.com/user-attachments/assets/72967d4f-2e29-4f16-b07c-ce60b6fe1a5c)

Synthesis
* This converts RTL(Register Transfer Level) to its circuits using Standard Cell Library components. Standard cells are the logic gates. * The resultant circuit described in HDL is called Gate Level Netlist. 
* The functions of the Gate Level are equivalent to the RTL

![image](https://github.com/user-attachments/assets/3e73bc1a-c232-4e6c-a781-134f110f024a)

* Standard cells
* They are the fundamental blocks
* Detailed view-GDSII & Abstract view- LEF

![image](https://github.com/user-attachments/assets/8ab2c19b-8b3e-4f23-9416-01e34a2b9a24)


Chip Floor Planning

![image](https://github.com/user-attachments/assets/4652412a-c479-4b69-a41c-919e94163113)

Macro Floor Planning

![image](https://github.com/user-attachments/assets/0c2bae11-9cbf-4111-bb1d-a00374501a42)

* Power Planning
* Power Planning has many layers. The upper metal layers are thick with low resistance and are used for power distribution. This is done to avoid IR drops and electron migration

![image](https://github.com/user-attachments/assets/5d38c66d-ef01-4be8-a58e-cc4c30fafe4a)

Placement

![image](https://github.com/user-attachments/assets/42bd45bc-6a5e-4630-a777-30adc2afe364)

* Global vs Detailed Placement
* Global: Tries to find the best position for the cells, which are not necessarily legal
* Detailed: The Global Placements are made legal, and the cells don't overlap

![image](https://github.com/user-attachments/assets/ce288c71-b2ba-4a90-b161-1c99a4c84188)

Clock-Tree Synthesis

![image](https://github.com/user-attachments/assets/bb289a87-0bc1-43bc-b1e3-10f80fb12c4b)

Clock skew is the arrival of the clock at different components at different times

Routing

![image](https://github.com/user-attachments/assets/7501b271-f18f-4548-831f-b23c7b985f1b)

![image](https://github.com/user-attachments/assets/2739ec37-8446-46b9-8a1c-880a710cc229)

The connection of the metal layers is determined via routing. The thickness of the metal layers is determined by the PDK.

Sign off

![image](https://github.com/user-attachments/assets/9cfb8921-93d0-47d8-89cc-619c4b899508)

3 kinds of verifications in the sign-off stage
* DRC: Checks whether the design fabrication rules are honoured by the final layout
* LVS: Checks the correspondence of the final layout functionality and gate-level netlist that we start with
* STA: Checks that the design runs under given clock frequencies


## DAY 1 Tasks
Calculate the flop ratio
**Flip-Flop**: is a circuit that can store and retrieve it whenever required. It can 'flip' & 'flop' as its name suggests, between 2 stable states, like X and X'

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

