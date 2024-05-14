
## AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using Vivado 2023.2.

## APPARATUS REQUIRED:
VIVADO 2023.2

## PROCEDURE:
STEP:1 Start the Vivado, Select and Name the New project.<br>
STEP:2 Select the device family, device, package and speed. <br>
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.<br>
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.<br>
STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.<br>
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

## Logic Gates
### Logic diagram:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/8d5f665a-8d79-4e20-b8b6-4aec6792457d)

### VERILOG CODE:
```
module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
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
### OUTPUT
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/d8486371-fb12-42c3-857b-a07769431d58)

## Half Adder
### Logic diagram:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/83b2aaa3-8d8c-49a7-b2a2-245f4b8f15c0)

### Verilog Code:
```
module halfadder(a,b,sum,carry);
input a,b;
output sum,carry;
xor g1(sum,a,b);
and g2(carry,a,b);
endmodule
```
## Output:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/899febaf-8dd9-437c-a020-7bfabc325744)

## Full Adder
### Logic Diagram:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/d5e881b8-9d24-44b5-9eb1-5da8c571fed1)

### Verilog Code:
```
module fadd(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
and g2(w2,a,b);
xor g3(sum,w1,c);
and g4(w3,w1,c);
or g5(carry,w3,w2);
endmodule
```
### Output:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/2d0e08a8-cf89-4c32-9573-d4b0dd3d7e21)

## Half Subtractor
### Logic Diagram:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/85538d37-8bb8-428f-b925-1948e5b9e110)

### Verilog Code:
```
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
xor g1(diff,a,b);
and g2(borrow,~a,b);
endmodule
```
### Output:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/c28eb265-4172-4333-9123-c8dac16d2896)

## Full Subtractor
### Logic Diagram:

![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/ccc4b436-a445-49e2-af3e-2e7384396226)

### Verilog Code:
```
module fs(a,b,bin,d,bout);
input a,b,bin; 
output d,bout;
wire w1,w2,w3;
xor g1(w1,b,bin; 
xor g2(d,w1,a);
and g3(w2,a,~w1);
and g4(w3,~b,bin);
or g5(bout,w2,w3);
endmodule
```
### Output:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/ba7ad7a8-a658-4349-850c-97afb4f251ab)

## 8 Bit Ripple Carry Adder
### Logic Diagram:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/22a9619d-ee7d-4548-ae14-9184b3305c52)

### Verilog Code:
```
module ripplemod(a, b, cin, sum, cout);
input [07:0] a;
input [07:0] b;
input cin;
output [7:0]sum;
output cout;
wire[6:0] c;
fulladd a1(a[0],b[0],cin,sum[0],c[0]);
fulladd a2(a[1],b[1],c[0],sum[1],c[1]);
fulladd a3(a[2],b[2],c[1],sum[2],c[2]);
fulladd a4(a[3],b[3],c[2],sum[3],c[3]);
fulladd a5(a[4],b[4],c[3],sum[4],c[4]);
fulladd a6(a[5],b[5],c[4],sum[5],c[5]);
fulladd a7(a[6],b[6],c[5],sum[6],c[6]);
fulladd a8(a[7],b[7],c[6],sum[7],cout);
endmodule
module fulladd(a, b, cin, sum, cout);
input a;
input b;
input cin;
output sum;
output cout;
assign sum=(a^b^cin);
assign cout=((a&b)|(b&cin)|(a&cin));
endmodule
```
### Output:
![image](https://github.com/Nandhak23/VLSI-LAB-EXP-1/assets/160568515/0bb04d3c-cd4a-42d1-8a09-32979492223b)

## RESULT:
Hence Logic Gates,Adders and Subtractor are simulated and synthesised using Vivado 2023.2.
