# DAY 2:  Good vs. Bad Floorplan and Introduction to Library Cells
##

### Utilisation and Aspect ratio
1. Defining the values of the core and die is the first of the physical design flow
2. We begin using a basic netlist, 2 flip flops, i.e. the launch flop and the capture flop.
> Note: A netlist explains the connectivity of an electronic design

3. There is a simple combinational logic connecting them
4. This netlist can be extrapolated to many kits
   
![image](https://github.com/user-attachments/assets/6227a15f-9499-4df3-8bce-c913a6069b1c)

5. The dimensions of the chip depend on the dimensions of the logic gates and flip-flops(not the wires)
   
![image](https://github.com/user-attachments/assets/f6c31011-f3e7-44c7-8511-a7f38a9406a0)

6. Assuming the dimensions of the standard cells and FFs as 1 unit.

![image](https://github.com/user-attachments/assets/68bdfaa8-c249-4de1-ada0-e5477c4f4056)

7. Next we calculate the area occupied by a netlist on a silicon wafer. For this, we rearrange the FFs and Standard cells accordingly, this way

![image](https://github.com/user-attachments/assets/1064e89c-8d0d-4183-bd91-5c5316eb0847)

8. All the logical cells are placed inside the core, i.e. inside the die. If the netlist occupies all of the core area, it's called **100% Utilisation**

```math
Utilisation\ factor = \frac{Area\ occupied\ by\ the\ netlist}{Total\ area\ of\ the\ core}
```

-> If the utilisation factor equals 1, then the core is filled with no extra place for cells, 

```math
Aspect\ Ratio = \frac{Height}{Width}
```
In this case, the aspect ratio equals 1, i.e. the core is a square, else, if it's 0.5 or 0.6 it's rectangular

### Pre-placed Cells
The arrangement of/ IPs in a chip is called **Floorplanning**. These IPs have user-defined locations and, are placed in a chip before automated placement and routing, known as pre-placed cells. Automated placement and routing tools place the remaining cells in the design onto the chip.
This is an example:

![image](https://github.com/user-attachments/assets/a29e02fc-86c8-4f9b-bf4e-cd87fd7f2bb6)

![image](https://github.com/user-attachments/assets/36858785-3dd3-4e7e-9603-4c1b02a58436)

![image](https://github.com/user-attachments/assets/09cc272c-5f8f-4ed0-8f63-4d70a98803ee)

The advantage of separating the 2 black boxes is that, they can be run separately, i.e. when the circuit has to run multiple times, these separated black boxes can be run once and then reused. 

```math
Core\ utilisation = \frac{Total\ area\ of\ the\ netlist}{Total\ area\ of\ the\ cell}
```
By default, the core utilisation % is set to 50

### De-coupling Capacitors
### Power Planning
### Pin placement & Logical cell placement blockage

## DAY 2 TASKS
#### Order of precedence (from lowest to highest)
System default - less.floorplan.tcl

config.tcl

sky130A_sky130_fd_sc_hd_config.tcl

### Lab
1. Run picorv32a on openLANE and get the desired output
Commands performed to invoke openLANE
> cd #Change the directory to openLANE

![image](https://github.com/user-attachments/assets/38ae0d5c-f0e7-4dc1-a2fe-a8d3949d460f)

![image](https://github.com/user-attachments/assets/1a3a0f4a-9342-49df-954f-0cd9163bce8b)


![image](https://github.com/user-attachments/assets/38809544-7105-4be2-9d5a-ee192b2016d6)

Metal layers have to be set as one less than the actual value

### Calculate the die area

![image](https://github.com/user-attachments/assets/b33bd477-d38f-4496-9a98-b23c9338d63b)

According to the floorplan def

```math
1\ micron = 1000\ Database\ Units
```
```math
Die\ width\ in\ unit\ distance = 660685 - 0 = 660685
```
```math
Die\ height\ in\ unit\ distance = 671405 - 0 = 671405
```
```math
Distance\ in\ microns = \frac{Value\ in\ Unit\ Distance}{1000}
```
```math
Die\ width\ in\ microns = \frac{660685}{1000} = 660.685\ Microns
```
```math
Die\ height\ in\ microns = \frac{671405}{1000} = 671.405\ Microns
```
```math
Area\ of\ die\ in\ microns = 660.685 * 671.405 = 443587.212425\ Square\ Microns
```

![image](https://github.com/user-attachments/assets/49bfc34e-b5d8-40d1-9d2b-3427ec9023ac)

![image](https://github.com/user-attachments/assets/96ce60e5-9e1b-414c-ad73-c0acc44de8aa)

![image](https://github.com/user-attachments/assets/2e2e3a82-5e4c-4ea4-ad51-343db720bc0c)

![image](https://github.com/user-attachments/assets/5c3b2d12-5e7d-4d86-96bf-2abae6e7f8ec)

![image](https://github.com/user-attachments/assets/29f630f8-7cb8-4a15-b255-c18e919809e8)

![image](https://github.com/user-attachments/assets/4d03de07-e4db-4320-9814-8b8cd7419048)

![image](https://github.com/user-attachments/assets/d39b7800-6b7f-4be9-9024-25bbf8031b0e)



## Library binding and Cell Placement
### Placement and Routing of Physical Design Flow
1. Bind netlist with physical cells
Taking an example of a simple netlist, with FFs and standard cells. Here, we can determine the function of these cells by their shape. However, in reality, the FFs & standard cells are square-shaped & rectangular. For this, the functions of the gates are given physical dimensions. After giving all the netlist components a standard shape, they look like this

![image](https://github.com/user-attachments/assets/bf8fd07c-b027-435e-ab38-e8cc3b5416dc)

This is a shelf arrangement that includes FFs, standard cells, and blocks. This can be called a library, the components of the netlist & blocks act as the books. The library consists of the information of the cells and their shape and size. Size of the cell is inversely proportionate to resistance path.

