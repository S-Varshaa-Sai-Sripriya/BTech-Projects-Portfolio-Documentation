# Verilog Implementation of T Flip-Flop using Xilinx ISE  

## Project Overview  
This project demonstrates the design and simulation of a T flip-flop using Verilog HDL in Xilinx ISE software. The T flip-flop is a fundamental sequential circuit element that toggles its output state based on the clock signal and input (T), serving as a building block for counters, registers, and control circuits.  

## Key Features  
- **Toggle Functionality**: Output toggles (0→1 or 1→0) when input T=1 at clock edges.  
- **Synchronous Operation**: Responds only to positive clock edges for reliable state transitions.  
- **Clear Signal**: Includes an asynchronous clear (Clr) to reset the output to 0.  
- **Verilog Implementation**: Modular design with testbench for simulation.  
- **Xilinx ISE Simulation**: Validated using waveform analysis.  

## Components  
1. **T Flip-Flop Core**:  
   - Inputs: `Clk` (clock), `T` (toggle), `Clr` (clear)  
   - Outputs: `Q` (state), `Qbar` (complementary state)  
2. **Testbench**:  
   - Generates clock cycles and test patterns for verification.  

## Working Principle  
1. **Normal Operation**:  
   - **T=0**: Output (`Q`) retains its current state.  
   - **T=1**: Output toggles on the rising clock edge.  
2. **Clear Mode**:  
   - When `Clr=0`, output resets to `Q=0` (and `Qbar=1`) immediately, overriding other inputs.  

## Verilog Code  
### T Flip-Flop Module  
```verilog  
module TFF (  
  input Clk, Clr, T,  
  output reg Q, Qbar  
);  
always @(posedge Clk) begin  
  if (Clr == 0) begin  
    Q <= 1'b0;  
    Qbar <= 1'b1;  
  end  
  else begin  
    case (T)  
      1'b0: {Q, Qbar} <= {Q, Qbar};      // No change  
      1'b1: {Q, Qbar} <= {~Q, ~Qbar};    // Toggle  
    endcase  
  end  
end  
endmodule  
```  

### Testbench  
```verilog  
module TFF_Testbench;  
  reg Clk, Clr, T;  
  wire Q, Qbar;  

  TFF T1 (Clk, Clr, T, Q, Qbar);  

  always #100 Clk = ~Clk;  // Clock generation  

  initial begin  
    Clk = 1'b1;  
    Clr = 1'b1;  
    T = 1'b0;  
    #100 Clr = 1'b0;      // Reset test  
    #100 Clr = 1'b1;  
    forever #50 T = ~T;   // Toggle input  
  end  
endmodule  
```  

## Simulation Results  
- **Waveform**: Captured in Xilinx ISE, showing:  
  - Toggling behavior when `T=1`.  
  - State retention when `T=0`.  
  - Immediate reset on `Clr=0`.  

## Applications  
- **Counters**: Divide clock frequency by 2.  
- **Control Circuits**: State machines and registers.  
- **Parallel Load Registers**: Data storage with toggle control.  

## Getting Started  
1. **Simulation**:  
   - Open Xilinx ISE and import the Verilog files.  
   - Run the testbench to generate waveforms.  
2. **Synthesis**:  
   - Target an FPGA (e.g., Spartan-6) to deploy the design.  

## Acknowledgments  
- **Amrita Vishwa Vidyapeetham, Chennai** for academic support.  
- **Mr. Devanathan B** (Faculty Guide) for project guidance.
