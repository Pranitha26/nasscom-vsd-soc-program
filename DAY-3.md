# DAY 3: Design Library cell using Magic Layout and NGspice characterisation
## DAY 3 Tasks
![image](https://github.com/user-attachments/assets/18cc067b-25f1-43d5-991f-df41129c4b96)

Cloning of the git repo and creating the magic layout

![image](https://github.com/user-attachments/assets/1c8c9f9a-f9e2-487a-8ae1-e64a68faa73a)
![image](https://github.com/user-attachments/assets/2dcc3cb7-8184-4564-8d09-31061d66a0c5)

![image](https://github.com/user-attachments/assets/ff6eb848-78e4-4a2d-a052-b16187f5d18b)

Y Output connectivity to PMOS & NMOS drains checked

![image](https://github.com/user-attachments/assets/a33306c7-9dbb-497e-8f18-b88348a30736)

Connectivity of the source of the PMOS to the VDD checked

![image](https://github.com/user-attachments/assets/9488f33c-2563-4d21-ae9e-3562cb3f6166)

NMOS to VCC(VGND) connection checked

![image](https://github.com/user-attachments/assets/9fb265a5-c951-49ce-afef-3869d80ba917)


Layout vs Lef
In the layout form, the logic is visible, however, in the abstract form or Lef, the logic is invisible to the user. This feature allows companies to protect their logic from their customers.

![image](https://github.com/user-attachments/assets/8d155751-7f31-48fe-a247-6de7d9693c6c)

![image](https://github.com/user-attachments/assets/8229eacb-90f6-4e63-80ee-bdcfbb0ec77f)

Click on the i key to edit. Change values according to the video to get a valid output. After editing, click on esc, then clicking : key takes you to the bottom line where wq! must be typed to save and exit.

![image](https://github.com/user-attachments/assets/cb4456f8-e33c-42bc-a05c-51ae3c460b74)

![image](https://github.com/user-attachments/assets/424213f2-7edb-4df6-87a0-1a52c87d9e5e)
After command ngspice sky130_inv.spice

![image](https://github.com/user-attachments/assets/e32b0060-aa4f-416a-8dcb-19b69e85473c)

Rise transition time calculation

```math
Rise\ transition\ time = Time\ taken\ for\ output\ to\ rise\ to\ 80\% - Time\ taken\ for\ output\ to\ rise\ to\ 20\%
```
```math
20\%\ of\ output = 660\ mV
```
```math
80\%\ of\ output = 2.64\ V
```
