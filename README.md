SR-FLIPFLOP-USING-CASE
AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/user-attachments/assets/5588dadd-770e-4245-af99-ef69102a7688)


This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/user-attachments/assets/6cfbf87a-5102-41f9-9499-f7b8ef7a9299)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/user-attachments/assets/97ef9a3c-5d84-44ca-9dc7-60b9f19c1b3a)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/user-attachments/assets/86770559-7e63-48e7-bda4-e259568510ac)


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

Procedure

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

PROGRAM

Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by:Sha Harieenesh
RegisterNumber:24002342
module EXP_6(q, q_bar, s,r, clk, reset);
  input s,r,clk, reset;
  output reg q;
  output q_bar;
 
  always@(posedge clk) begin 
    if(!reset)       
			q <= 0;
    else 
  begin
      case({s,r})       
	     2'b00: q <= q;    
        2'b01:q<=1'b0;  
        2'b10:q<=1'b1;   
        2'b11:q<=1'bx;   
      endcase
    end
  end
  assign q_bar = ~q;
endmodule
RTL LOGIC FOR FLIPFLOPS 
![image](https://github.com/user-attachments/assets/35ce22ac-9817-4666-8b4a-94c5a9a99c59)


TIMING DIGRAMS FOR FLIP FLOPS 
![image](https://github.com/user-attachments/assets/a6f3c1cf-6388-404b-97f6-932fdda2b0d2)


RESULTS

The observation of the simulation results and confirm the successful execution of the program.
