# Experiment--05-Implementation-of-flipflops-using-verilog
## NAME : BEATRICE THOMAS
## REG NO:23005036
### AIM: To implement all the flipflops using verilog and validating their functionality using their functional tables
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 
### SR Flip-Flop
SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://user-images.githubusercontent.com/36288975/167910294-bb550548-b1dc-4cba-9044-31d9037d476b.png)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied.

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is
Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)


### JK Flip-Flop
JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.
![image](https://user-images.githubusercontent.com/36288975/167910378-d2d984a7-2815-4d17-8c41-ee4bdf59ec24.png) 

 
This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. 

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is
Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)



### Procedure
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:*
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6.*Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.



### PROGRAM 
 S R FLIP FLOP

 module flipflops(S,R,clk,Q,Qbar);
	
 input S,R,clk;
	
 output reg Q;
	
 output reg Qbar;
	
 initial Q=0;
	
 initial Qbar=1;
	
 always @(posedge clk)

 begin
	
 Q=S|((~R)&Q);
	
 Qbar=R|((~S)&(Qbar));
	
 end
 
 endmodule

 J K FLIP FLOP :

module flipflops(J,K,clk,Q,Qbar);

input J,K,clk;

output reg Q;

output reg Qbar;

initial Q=0;

initial Qbar=1;

always @(posedge clk)

begin

Q=(J&(~Q))|((~K)&Q);

Qbar=((~J)&(Qbar))|K&(~Qbar);

end

endmodule


### RTL LOGIC FOR FLIPFLOPS 

S R FLIP FLOP :

<img width="335" alt="ffsr rtl" src="https://github.com/23005036/Experiment--05-Implementation-of-flipflops-using-verilog/assets/140035214/7936ff5f-9f7a-4da1-a1e3-c504ac0ba3ab">


J K FLIP FLOP :

<img width="470" alt="j k ff rtl" src="https://github.com/23005036/Experiment--05-Implementation-of-flipflops-using-verilog/assets/140035214/b03767d7-a850-403e-b79d-a623dbebe430">



### TIMING DIGRAMS FOR FLIP FLOPS 

S R FLIP FLOP : 

![S R FF](https://github.com/23005036/Experiment--05-Implementation-of-flipflops-using-verilog/assets/140035214/38e95999-506e-4747-ab91-9b5315e39ba2)

 J K FLIP FLOP :

 ![jk fll](https://github.com/23005036/Experiment--05-Implementation-of-flipflops-using-verilog/assets/140035214/87a28df1-33d0-42b6-b8bf-a56d7b966afe)



### RESULTS 
 Thus both SR and JK flipflops are verified using verilog programming. The state table, rtl realization,timing diagram are represented here.
