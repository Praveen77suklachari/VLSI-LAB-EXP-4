# VLSI-LAB-EXP-4
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7
Spartan6 FPGA

**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
PROCEDURE:
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

# SR FLIPFLOP
# Logic Diagram:
![329867006-fbe616e5-5ab9-4c07-a783-4c7f7ee11882](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/93d42bca-b5c3-4f97-b155-dd73ac18b941)

# VERILOG CODE:
```
module srff(s,r,clk,rst,q);
input s,r,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({s,r})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=1'bX;
endcase
end
end
endmodule
```
# Output:
![329867125-309f6edb-f6ad-484f-8482-d9bd511c0d82](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/33d85552-c54f-4617-b5d1-dbd72a33f537)

# JK FLIPFLOP
# Logic Diagram:
![329867167-18244d09-218a-49a3-b4af-5c9c118a4af6](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/8d278a0c-50a1-4ab1-978d-1bf39c269e3e)

# verilog code:
```
module jkff(j,k,clk,rst,q);
input j,k,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({j,k})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=~q;
endcase
end
end
endmodule
```
![329867200-64e2f447-d90d-4cf0-8320-b17f15571030](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/128db912-4ab0-4943-87c1-5783e3bec269)
# T FLIPFLOP
# Logic Diagram:
![329867220-67c30263-472a-4006-bacb-5bbb12bc0502](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/5d194b51-34f1-47e1-89ae-ad61065a0588)

# verilog code:
```
module tff(clk,rst,t,q);
input clk,rst,t;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else if (t==0)
q=q;
else
q=~q;
end
endmodule
```
# Output:
![329867292-10041479-fa31-40e1-9628-ee690a5cbfeb](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/9ccc7a27-eff6-4006-8a9c-f10bbe26e09b)

# D FLIPFLOP
# Logic Diagram:
![329867310-e48cce71-cc09-42cd-be41-f829c7bf2543](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/45d288df-4138-442f-ab2d-07fb0b2b1ed1)
# verilog code:
```
module dff(d,clk,rst,q);
input d,clk,rst;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else
q=d;
end
endmodule
```
# Output:
![329867342-b78d094f-3cdc-46be-a19e-733bc688ebe9](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/5f18ddba-e483-49f9-9025-001f9135fc54)

# COUNTER
# Logic Diagram
![329867381-f1de807f-b5df-401a-8df3-f607262044bd](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/1e346996-df8d-4264-a7f2-bd3a414a1718)
# verilog code:
```
module udc(clk,rst,updown,out);
input clk,rst,updown;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1)
out=4'b0000;
else if(updown==1)
out=out+1;
else
out=out-1;
end
endmodule
```
# Output:
![329867423-27e42464-ecb4-4b40-96e1-ce2db4cc4ad1](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/40726fcd-8776-4a5c-aed8-7736467c69f8)

# Mod-10 Counter:
# Logic Diagram:
![329867434-e4884268-0275-4051-8eec-92d0ab75e6a5](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/29b13ba6-db22-4ee0-88fe-2b16136da928)
# verilog code:
```
module mod10(clk,rst,out);
input clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1 | out==4'b1001)
out=4'b0000;
else
out=out+1;
end
endmodule
```
# Output:
![329867464-d3203f3c-2e71-4235-9218-aead1987d6ae](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/853bbd36-e795-4dc1-bb44-14089558a44f)

# Ripple Carry Counter:
# Logic Diagram:
![329867500-d7e5d649-b86b-4abb-a3ac-75a5188befcf](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/8622a00c-f7b9-4b51-b23b-d8597fe03547)

# verilog code:
```
module tff(q,clk,rst);
input clk,rst;
output q;
wire d;
dff df1(q,d,clk,rst);
not n1(d,q);
endmodule

module dff(q,d,clk,rst);
input d,clk,rst;
output q;
reg q;
always @(posedge clk or posedge rst)
begin
if (rst)
q=1'b0;
else 
q=d;
end
endmodule

module rcc(clk,rst,q);
input clk,rst;
output [3:0]q;
tff tf1(q[0],clk,rst);
tff tf2(q[1],q[0],rst);
tff tf3(q[2],q[1],rst);
tff tf4(q[3],q[2],rst);
endmodule
```
# Output:
![329867556-9003f202-e261-463c-a9b0-9f32ba596a0f](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/124765056/3f2d357d-5f1f-472a-9c98-2023e68bdcc0)

# RESULT
Hence SR, JK, T, D - FLIPFLOP, COUNTER DESIGN are simulated and synthesised using Xilinx ISE.



