# RTL Design – 8-bit ALU

This directory contains the **Register Transfer Level (RTL)** implementation of an **8-bit Arithmetic Logic Unit (ALU)** along with its **testbench** and a **representative simulation waveform** used for functional verification.


## 📁 Contents
rtl/

 - ALU_8bit.v                         # Verilog RTL implementation of the 8-bit ALU
 - ALU_8bit_TB.v                           # Testbench for functional verification
 - output_waveform.png                # Simulation waveform snapshot


##  ALU Description

The 8-bit ALU supports a variety of **arithmetic and logical operations**, selected using a control signal (`ALU_Sel`).  
The design is **synchronous**, operating with a clock and reset, and generates standard status flags.

### Supported Operations
- Addition
- Subtraction
- AND
- OR
- XOR
- NOT
- Increment
- Decrement
- Multiplication

### Status Flags
- **CarryOut** – Indicates carry/borrow from arithmetic operations  
- **Zero** – Set when the output is zero  
- **Sign** – Indicates the sign of the result  
- **Overflow** – Detects arithmetic overflow  

##  Module Interface

**Inputs**
- `clk` – Clock signal
- `rst` – Active-low reset
- `A [7:0]` – Operand A
- `B [7:0]` – Operand B
- `ALU_Sel [3:0]` – Operation select

**Outputs**
- `ALU_Out [15:0]` – ALU result
- `CarryOut` – Carry/borrow flag
- `Zero` – Zero flag
- `Sign` – Sign flag
- `Overflow` – Overflow flag


##  RTL Verification

The RTL was verified using a **Verilog testbench (`ALU_8bit_TB.v`)** that applies different input combinations and ALU control signals.  
Simulation was performed using **Icarus Verilog (iverilog)**, and signal behavior was analyzed using **GTKWave**.


##  Simulation Waveform

![ALU RTL Simulation Waveform](output_waveform.png)

##  Next Stage

This verified RTL serves as the input to the OpenLane RTL-to-GDSII flow, where the design is synthesized, placed, routed, and physically verified using Sky130 standard cells.


