# AIM: 
 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Xilinx ISE.
 
#  APPARATUS REQUIRED:
Vivado 2023.2

# LOGIC DIAGRAM

# SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


# JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

# T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


# D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


# COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
# PROCEDURE:
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
![321309163-1b2177a8-188e-4f48-b15a-d7c9b8593b3b](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/fbe616e5-5ab9-4c07-a783-4c7f7ee11882)

# verilog code:
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
![321309519-fde5adbc-d127-43c7-9c3a-c97e33c69621](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/309f6edb-f6ad-484f-8482-d9bd511c0d82)

# JK FLIPFLOP
# Logic Diagram:
![321309704-fe2a5529-43ac-4082-8cac-c76d3b0e7b7c](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/18244d09-218a-49a3-b4af-5c9c118a4af6)

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
# Output:
![321310017-b12acba8-0471-448a-8dc6-4bc19cde4bc3](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/64e2f447-d90d-4cf0-8320-b17f15571030)

# T FLIPFLOP
# Logic Diagram:
![321310411-697518d6-da49-48c9-85b5-91688460a237](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/67c30263-472a-4006-bacb-5bbb12bc0502)

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
![321310826-1d84bc96-d7b9-44bf-9f1b-b1793188a121](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/10041479-fa31-40e1-9628-ee690a5cbfeb)

# D FLIPFLOP
# Logic Diagram:
![321311726-d09dddf0-3f9f-4e6d-9f69-3787c39000d2](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/e48cce71-cc09-42cd-be41-f829c7bf2543)

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
![321312052-0daf167d-d841-4311-8c4a-278de39d27c4](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/b78d094f-3cdc-46be-a19e-733bc688ebe9)

# COUNTER
# Logic Diagram
![321312544-15be6215-2b4d-48e6-8f2e-d6932e27e3b0](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/f1de807f-b5df-401a-8df3-f607262044bd)

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
![321313237-fd74457f-1f35-4e94-a628-5efff9ba956f](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/27e42464-ecb4-4b40-96e1-ce2db4cc4ad1)

# Mod-10 Counter:
# Logic Diagram:
![321313412-637add02-e848-4f74-a8b8-9e183a68df4b](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/e4884268-0275-4051-8eec-92d0ab75e6a5)

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
![321313630-20fb126a-6ff9-48a3-876f-64c9b710f28c](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/d3203f3c-2e71-4235-9218-aead1987d6ae)

# Ripple Carry Counter:
# Logic Diagram:
![321313815-c8966ae1-c506-4bfc-a6e3-028ea15d87a2](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/d7e5d649-b86b-4abb-a3ac-75a5188befcf)

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
![321314073-9738870c-f3e1-40a5-87be-5a6cb680ca91](https://github.com/alvin-2003/VLSI-LAB-EXP-4/assets/163816866/9003f202-e261-463c-a9b0-9f32ba596a0f)

 # RESULT:
Hence SR, JK, T, D - FLIPFLOP, COUNTER DESIGN are simulated and synthesised using Vivad0 2023.
