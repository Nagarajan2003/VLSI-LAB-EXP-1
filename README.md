# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
```
full adder(code):
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
```
OUTPUT:

full adder (design):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/c00dfa5e-0261-4ac9-8353-264c94e7f3cf)
full adder(sim):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/d40fd61d-646a-447e-a04a-4b99a4bd2979)

half adder(code):
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
output:
half adder(sim):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/f6f7e6a6-b0b6-4d2d-8f62-d4d9d80c7345)
half adder(design):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/422b68d7-29d5-4266-afa8-8456f05fc359)



half sub(code):
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
OUTPUT:
half sub(design):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/9be2426b-9f03-4e73-860c-d11c94d6e448)
half sub(sim):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/f57915b9-7669-4ed4-b6f2-d46e1df039e5)



full sub(code):
```
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```

output:
full sub(sim):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/119024ee-1de3-43d5-8833-3f6a930c9165)

full sub(design):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/2779fde7-0015-4282-9560-7c2ad5c403fa)

logicgates(code):
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
output:

logicgates(sim):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/41af7ce7-e6af-4281-b556-dcc13dfd1aff)

logicgates(design):
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/e1219f05-ef53-47e7-b5d6-afee83f0eadf)





RESULT:

