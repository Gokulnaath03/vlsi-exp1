# vlsi-exp1

#AIM:To simulate and synthesis logic gates,adders and substractor using VIVADO.

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


























#HALF ADDER:















#PROGRAM:
module HA (a, b, sum, carry);
input a, b;
output sum, carry;
xor g1(sum, a, b);
and g2 (carry, a, b);
endmodule


#OUTPUT:


















#HALF SUBTRACTOR:
















#PROGRAM:
module HS (a, b, diff, borrow);
input a, b;
output diff, borrow;
xor gl (diff, a, b);
and g2 (borrow, ~a, b);
endmodule


#OUTPUT:























#FULL ADDER:


















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


























#FULL SUBTRACTOR:



















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



























#8-BIT RIPPLE CARRY-ADDER:





















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






























#RESULT:Thus, the logic gates and 4 Bit of Adder and Subtractor are
 Implemented and simulated successfully.
