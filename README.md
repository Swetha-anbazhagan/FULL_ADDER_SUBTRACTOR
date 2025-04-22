# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

Full Adder

![WhatsApp Image 2025-04-22 at 22 35 21_5d8b5641](https://github.com/user-attachments/assets/6900f1a0-986f-49d3-9089-0bb6d61e675c)

Full Subtractor 

![WhatsApp Image 2025-04-22 at 22 35 28_d3914300](https://github.com/user-attachments/assets/320ce89b-b830-4ef5-8385-98cf4c9795ca)


**Program:**

 Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
 
 ```
 Developed by:Swetha A
 RegisterNumber:212224040343
 
 module FAS(a, b, c, sum, carry);
    input a;
    input b;
    input c;
    output sum;
    output carry;
	 reg sum,carry;
	 reg t1,t2,t3;
	 always @ (a or b or c) begin
	 sum = (a^b)^c;
	 t1=a & b;
	 t2=b & c;
	 t3=a & c;
	 carry=(t1 | t2) | t3;
	 end
endmodule

module FAS1(a, b, cin, diff, borrow);
    input a;
    input b;
    input cin;
    output diff;
    output borrow;
	 reg t1,t2,t3;
	 reg diff,borrow;
	 reg abar;
	 always @ (a or b or cin) begin
	 abar= ~ a;
	 diff = (a^b)^cin;
	 t1=abar & b;
	 t2=b & cin;
	 t3=cin & abar;
	 borrow=(t1 | t2) | t3;
	 end
	endmodule
 ```

**RTL Schematic**

![WhatsApp Image 2025-04-22 at 22 21 19_678c1848](https://github.com/user-attachments/assets/f1166d29-86d1-488a-8b1f-014c033b2df1)
![WhatsApp Image 2025-04-22 at 22 31 57_cee5cf89](https://github.com/user-attachments/assets/66906b4e-4718-4772-aa54-23bab328de3b)




**Output Timing Waveform**

![WhatsApp Image 2025-04-22 at 22 21 19_da587ec0](https://github.com/user-attachments/assets/43970d1a-4281-46e1-9825-517bcd0ccf38)
![WhatsApp Image 2025-04-22 at 22 31 59_bd5bff7f](https://github.com/user-attachments/assets/21cd21e8-5621-4957-a4d4-a4c2ca6dbc33)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



