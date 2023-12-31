## NAME: MALENI.M
## REGISTER NUMBER: 212223040110
## Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## THEORY:

Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## PROCEDURE:
1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow. 

5.End the verilog program using keyword endmodule.

## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/41d24926-a5f6-48b6-822d-58d5654de956)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## PROGRAM:
module project_4_1(a,b,borrow,diff);	                                                   
input a,b;
output borrow,diff;
assign borrow=~a&b;
assign diff=a^b;
endmodule

## RTL REALIZATION:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/f7a311be-72da-4fbd-afa0-49e55ca17572)
## TRUTH TABLE:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/880527e7-8324-47f1-99a3-7bbd7739e0f3)
## TIMING DIAGRAM:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/598d1d93-838e-4f02-b04e-854048871872)

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/99d92dcc-f55c-4bbc-8543-9a62d181c2fd)

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## PROGRAM:
module project_4_2(a,b,bin,borrow,diff);	                                               
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule

## RTL REALIZATION:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/33d35784-00c6-46ca-a8d3-ab30c6414d91)
## TRUTH TABLE:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/199912c5-74e4-4171-924d-31dcf13fab1d)

## TIMING DIAGRAM:
![image](https://github.com/MALENIMURUGAN/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/144870675/d8f8c781-52ac-4322-8ef3-287ec4cf40d4)

## RESULT:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
