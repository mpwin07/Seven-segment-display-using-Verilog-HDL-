# SEVEN SEGMENT DISPLAY USING VERILOG HDL
# Aim
To design and simulate a seven-segment display driver using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 environment. The objective is to implement the logic that converts a 4-bit binary input into the corresponding 7-segment display output for the digits 0 to 9.

# Apparatus Required
Vivado 2023.1
Computer system with a suitable operating system.

# Procedure

Launch Vivado 2023.1:

Open Vivado and create a new project.
Design the Verilog Code:

Write the Verilog code for the seven-segment display, defining the logic that maps a 4-bit binary input to the corresponding segments (a to g) of the display.
Create the Testbench:

Write a testbench to simulate the seven-segment display behavior. The testbench should apply various 4-bit input values and monitor the corresponding output on the seven-segment display.
Add the Verilog Files:

Add both the design module and the testbench in the Vivado project.
Run Simulation:

Run the behavioral simulation to verify the output. Ensure the seven-segment display behaves correctly for binary inputs 0000 to 1001 (decimal 0 to 9).
Observe the Waveforms:

Analyze the output waveforms in the simulation window, and verify that the correct segments light up for each digit.
Save and Document Results:

Capture screenshots of the waveform and save the simulation logs. These will be included in the lab report.

# Diagram
![image](https://github.com/user-attachments/assets/d7ecb419-906e-4e3b-9b82-f86ced4f364a)


# Verilog Code for Seven-Segment Display
```
module seven_segment_display ( input wire [3:0] binary_input, output reg [6:0] seg_output ); always @(*) begin case (binary_input) 4'b0000: seg_output = 7'b0111111;
4'b0001: seg_output = 7'b0000110;
4'b0010: seg_output = 7'b1011011;
4'b0013: seg_output = 7'b1001111;
4'b0100: seg_output = 7'b1100110; 4'b0101: seg_output = 7'b1101101;
4'b0110: seg_output = 7'b1111101;
4'b0111: seg_output = 7'b0000111;
4'b1000: seg_output = 7'b1111111; 4'b1001: seg_output = 7'b1101111;
default: seg_output = 7'b0000000;
endcase end endmodule
```

output:![WhatsApp Image 2024-10-05 at 15 09 29_48e80470](https://github.com/user-attachments/assets/c73e36a5-1924-4ddb-b6bd-df3cad21b851)


Testbench for Seven-Segment Display:
```
module seven_seg_tb;
reg[3:0]bcd; 
wire[6:0]seg; 
sevensegment07 uut( .bcd(bcd), .seg(seg) ); 
initial begin bcd =4'b0000; 
#2 bcd=4'b0000; 
#2 bcd=4'b0001; 
#2 bcd=4'b0010; 
#2 bcd=4'b0011; 
#2 bcd=4'b0100; 
#2 bcd=4'b0101; 
#2 bcd=4'b0110; 
#2 bcd=4'b0111; 
#2 bcd=4'b1000; 
#2 bcd=4'b1001; 
#2 $stop; 
end 
endmodule

```
output:![WhatsApp Image 2024-10-05 at 15 09 57_2fae5c34](https://github.com/user-attachments/assets/fc93e2cc-5418-4cfb-b60a-b69645a9219a)


# Conclusion
In this experiment, a seven-segment display driver was successfully designed and simulated using Verilog HDL. The simulation results confirmed that the display correctly represented the digits 0 to 9 based on the 4-bit binary input. The testbench effectively verified the functionality of the seven-segment display by applying various input combinations and observing the corresponding segment outputs. This experiment highlights how Verilog HDL can be used to control hardware components like a seven-segment display in digital systems.
