# DAY 2:  Good vs. Bad Floorplan and Introduction to Library Cells
##

### Utilisation and Aspect ratio
1. Defining the values of the core and die is the first of the physical design flow
2. We begin using a basic netlist, 2 flip flops, i.e. the launch flop and the capture flop.
> Note: A netlist defines the connectivity of an electronic design

3. There is a simple combinational logic connecting them
4. This netlist can be extrapolated to many kits
   
![image](https://github.com/user-attachments/assets/6227a15f-9499-4df3-8bce-c913a6069b1c)

5. The dimensions of the chip depend on the dimensions of the logic gates and flip-flops(not the wires)
   
![image](https://github.com/user-attachments/assets/f6c31011-f3e7-44c7-8511-a7f38a9406a0)

6. Assuming the dimensions of the standard cells and FFs as 1 unit.

![image](https://github.com/user-attachments/assets/68bdfaa8-c249-4de1-ada0-e5477c4f4056)

7. Next we calculate the area occupied by a netlist on a silicone wafer. For this, we rearrange the FFs and Standard cells accordingly, this way

![image](https://github.com/user-attachments/assets/1064e89c-8d0d-4183-bd91-5c5316eb0847)

8. All the logical cells are placed inside the core, i.e. inside the die. If the netlist occupies all of the core area, it's called **100% Utilisation**

```math
Utilisation\ factor = frac\{Area\ occupied\ by\ the\ netlist}{Total\ area\ of\ the\ core}
```


## DAY 2 TASKS
#### Order of precedence (from lowest to highest)
System default - less.floorplan.tcl

config.tcl

sky130A_sky130_fd_sc_hd_config.tcl

### Lab
1. Run picorv32a on openLANE and get the desired output
2. Calculate


![image](https://github.com/user-attachments/assets/38809544-7105-4be2-9d5a-ee192b2016d6)
