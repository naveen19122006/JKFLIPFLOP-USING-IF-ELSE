# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
Step1: Define the specifications and initialize the design.
Step2: Declare the name of the entity and architecture by using VHDL source code.
Step3: Write the source code in VERILOG.
Step4: Check the syntax and debug the errors if found, obtain the synthesis report.
Step5: Verify the output by simulating the source code.
Step6: Write all possible combinations of input using the test bench.
Step7: Obtain the place and route report.


**PROGRAM**

~~~
module jk (
input clk,    
input reset,  
input j,      
input k,      
output reg q, 
output reg q_bar 
);
always @(posedge clk or posedge reset) begin
if (reset) begin
q <= 1'b0;       
q_bar <= 1'b1;   
end
else begin
case ({j, k})
2'b00: ;              
2'b01: begin          
q <= 1'b0;
q_bar <= 1'b1;
end
2'b10: begin          
q <= 1'b1;
q_bar <= 1'b0;
end
2'b11: begin          
q <= ~q;
q_bar <= ~q_bar;
end
endcase
end
end
endmodule
~~~

**RTL LOGIC FOR FLIPFLOPS**
![Screenshot 2024-12-14 031908](https://github.com/user-attachments/assets/d39d87a4-78da-4d8f-84d0-523b3f8a061d)

**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot 2024-12-14 032257](https://github.com/user-attachments/assets/b7c172a5-3f15-4e94-95fb-9a626bb2b7c0)

**RESULTS**

Thus the OUTPUT of JK Flip Flops are verified by synthesizing and simulating the VERILOG
code
