# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure:
1.Create a project with required entities.

2.Create a module along with respective file name.

3.Run the respective programs for the given boolean equations.

4.Run the module and get the respective RTL outputs.

5.Create university program(VWF) for getting timing diagram.

6.Give the respective inputs for timing diagram and obtain the results.

## Program:
```
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: M.Vidya Neela
RegisterNumber:  212221230120
*/
```
```
using NAND:
   module combo1(a,b,c,d,f);
   input a,b,c,d;
   output f;
   wire p,q,r;
   assign p=(~c & b & a);
   assign q=(~d & c & ~a);
   assign r=(c & ~b & a);
   assign f=(~(~p & ~q & ~r));
   endmodule

using NOR:
   module combo2(a,b,c,d,f);
   input a,b,c,d;
   output f;
   wire p,q,r;
   assign p=( c & ~b & a);
   assign q=( d & ~c & a);
   assign r=( c & ~b & a);
   assign f=(~(~( p | q | r)));
   endmodule
```
## RTL realization

## Output:
##USING NAND GATE:
## RTL
![201718116-a5fdde93-6d4d-419f-9a69-f2cde7592339](https://user-images.githubusercontent.com/94169318/202910579-78561090-052c-4d4e-8cd1-a2860797d3d7.png)

## Timing Diagram
![201718260-e96daad5-d651-4f6c-9f1a-a9c7562ac2be](https://user-images.githubusercontent.com/94169318/202910590-ccd9094a-d2c3-48d0-b057-94335623bf92.png)

## Truth Table
![201718407-80fb80b5-313e-444b-bb6d-f45d44edfa03](https://user-images.githubusercontent.com/94169318/202910610-05ac5fe7-4d11-458f-9674-792d2b0abda7.png)

## USING NOR:
## RTL:
![201718664-b17128cc-4b2b-4f80-a06e-f1543f7e30d0](https://user-images.githubusercontent.com/94169318/202910689-8d5b1fcd-8391-45bf-894f-dac9ddc34853.png)

## Timing Diagram
![201718815-48016746-e2b7-4e32-a708-2383fbd170ae](https://user-images.githubusercontent.com/94169318/202910706-09b9992e-e782-4251-843f-4da81ac9ef79.png)

## Truth Table
![201718953-4b73644d-65f8-485d-a765-d1c60ce7b449](https://user-images.githubusercontent.com/94169318/202910715-599bbaa4-2d46-4d7c-91dd-f0495a203784.png)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
