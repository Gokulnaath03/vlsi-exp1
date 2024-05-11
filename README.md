# vlsi-exp1

#AIM:To simulate and synthesis logic gates,4  adders and substractor using VIVADO.

#APPARATUS REQUIRED:VIVADO 2023.2

#PROCEDURE:
STEP:1 Start the Vivado, Select and Name the New project.
STEP:2 Select the device family, device, package and speed.
STEP:3 Select new source in the New Project and select Verilog Module
as the Source type.
STEP:4 Type the File Name and Click Next and then finish button. Type
the code and save it.
STEP:5 Select the Behavioural Simulation in the Source Window and
click the check syntax.
STEP:6 Click the simulation to simulate the program and give the inputs
and verify the outputs as per the truth table.


#LOGIC GATES:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/48aa8480-8544-48f5-bdbb-1f7c9a11f4b2)


#PROGRAM:
module LG(a, b, c0, c1, c2, c3, c4, c5, c6);
input a, b;
output c0, c1, c2, c3, c4, c5, c6;
and(c0, a, b);
or(c1, a, b);
xor(c2, a, b);
nand(c3, a, b);
nor(c4, a, b);
xnor(c5, a, b);
not(c6, a);
endmodule



OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/e78c1ace-1412-446f-9902-a1f5361be7da)



#HALF ADDER:


![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/115e403a-bf53-4d02-b10e-dbf6bc1ff749)


#PROGRAM:
module HA (a, b, sum, carry);
input a, b;
output sum, carry;
xor g1(sum, a, b);
and g2 (carry, a, b);
endmodule


#OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/85ea124c-5422-4abd-ae75-44b6ecf60f57)



#HALF SUBTRACTOR:


![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/b0eefd7b-8f91-4cb1-98a1-efdaaefe6d19)



#PROGRAM:
module HS (a, b, diff, borrow);
input a, b;
output diff, borrow;
xor gl (diff, a, b);
and g2 (borrow, ~a, b);
endmodule


#OUTPUT:


![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/f29a2908-8e11-4721-a9f1-b61e11d9f501)



#FULL ADDER:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/34d91575-840e-46b4-ac9d-0f5eaa2e32b9)

#PROGRAM:
module FA(a, b, c, sum, carry);
input a, b, c;
output sum, carry;
wire w1, w2, w3;
xor g1(w1, a, b);
and g2(w2, a, b);
xor g3(sum, w1 ,c);
and g4(w3, w1, c);
or g5(carry, w3, w2);
endmodule


#OUTPUT:


![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/51461123-ef71-45e3-8c6b-6ddd5cc34c2f)



#FULL SUBTRACTOR:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/6dd45df6-26fe-4c78-a9b6-50ec43ff23cb)


#PROGRAM:
module FS(a, b, c, diff, borrow);
input a, b, c;
output diff, borrow;
wire x, y, z;
xor g1(x, a, b);
and g2(y, ~a , b);
xor g3(diff, x, c);
and g4(z, c, ~x);
or g5(borrow, y, z);
endmodule


#OUTPUT:


![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/6fc03d8e-920d-4f83-8d46-aa53f072c6c7)


#8-BIT RIPPLE CARRY-ADDER:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/87e20862-0b30-42da-8973-d6ec27dbe28a)

#PROGRAM:
module FA(a, b, c, sum, carry);
input a, b, c;
output sum, carry;
assign sum=a ^ b ^ c;
assign carry=a & b|b & c|a & c;
endmodule
module RCA(a, b, c, sum, carry);
input [7:0] a, b;
input c;
output [7:0] sum;
output carry;
wire [6:0] w;
FA f1(a[0], b[0], c, sum[0], w[0]);
FA f2(a[1], b[1], w[0], sum[1], w[1]);
FA f3(a[2], b[2], w[1], sum[2], w[2]);
FA f4(a[3], b[3], w[2], sum[3], w[3]);
FA f5(a[4], b[4], w[3], sum[4], w[4]);
FA f6(a[5], b[5], w[4], sum[5], w[5]);
FA f7(a[6], b[6], w[5], sum[6], w[6]);
FA f8(a[7], b[7], w[6], sum[7], carry);
endmodule


#OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-exp1/assets/167178811/2ec30dfe-a824-49a1-a021-a7fcd3407def)



#RESULT:Thus, the logic gates and 4 Bit of Adder and Subtractor are
 Implemented and simulated successfully.
