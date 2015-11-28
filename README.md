Using the 4-bit ALU from Project 2 write a Verilog implementation of a simple 4-bit CPU. First you have to build (or use) the following modules:

9-bit instruction register using nine D flip-flops (use D_flip_flop.vl). Include a clock pulse input that goes to all D flip-flops. Use gate level modeling.
Register file (use the module provided in the template).
4-bit ALU. This is the module you have implemented in Project 2.
LI instruction decoder. This is a module implementing a combinational circuit which outputs 0 when the LI opcode (100) is present at its inputs, and 1 otherwise. Use gate level modeling.
Quadruple 2x1 multiplexer (mulitplexing 4-bit data) for the write data input of the register file. Use gate level modeling.
Build the CPU as discussed in class Designing a CPU. Use the tempalte provided in CPU_Template.vl. Read carefully the comment and add code as suggested.

Testing. Create a test module that simulates running the following program on the CPU by loading the instruction register with the corresponding binary values for each instruction. Monitor the result of the execution of each instruction on the write data input of the register file.

LI  $2, 15       # load decimal 15 (unsigned binary) into $2 
LI  $3, 8        # load decimal 8 (unsigned binary) into $3 
AND $1, $2, $3   # $1 = $2 AND $3 (two's complement -8) 
SUB $3, $1, $2   # $3 = $1 - $2 = -8 - (-1) = -7 
SLT $2, $3, $0   # $2 = 1 ($3 < 0) 
ADD $1, $2, $3   # $1 = $2 + $3 = 1 + (-7) = -6 
SUB $1, $0, $1   # $1 = $0 - $1 = 0 - (-6) = 6 
OR  $3, $1, $2   # $3 = $1 OR $2 = 7
