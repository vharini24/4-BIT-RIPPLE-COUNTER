# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */
1. Create New Project
2. Create Verilog/VHDL File
3. Compile the Design
4. Simulate Using Waveform
5. Verify Output

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by: V. HARINI RegisterNumber: 212225040113
*/

module ripcounter(clk,rst,t,A,B,C,D); 
input clk,rst,t; 
output A,B,C,D;
wire A,B,C,D;

TFlipFlop T0(D,clk,rst,t); 
TFlipFlop T1(C,D,rst,t); 
TFlipFlop T2(B,C,rst,t); 
TFlipFlop T3(A,B,rst,t); 

endmodule 

module TFlipFlop(q,clk,rst,t); 
input clk,rst,t; 
output reg q;

always @(posedge clk) 
begin 
    if(!rst)
        q <= 0;
    else
        q <= (t ? ~q : q);
end

endmodule

**RTL LOGIC FOR 4 Bit Ripple Counter**


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

**RESULTS**
The ripple counter was successfully designed and implemented using Quartus Prime.
The simulation results showed that the counter outputs changed sequentially in binary form with each clock pulse.Hence, the experiment was verified successfully.
