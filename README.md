## Nanoprocessor
![pikaso_texttoimage_Nanoprocessor](https://github.com/RanaweeraHK/Nanoprocessor/assets/129282753/dd2f124a-1f14-4ac9-b894-7fea037cc45c)

In the second semester of the course In21-S2-CS1050 - Computer Organization and Digital Design, we created a nanoprocessor.

This project is an implementation of a system combining the Slow_Clk and Nanoprocessor components. The system is designed to showcase functionality by displaying the numbers 0, 1, 3, and 6 sequentially on a seven-segment display. The LUT_7seg (ROM module) is utilized to store specific values for the seven-segment display.

## Components
The system comprises three main components:

**Slow_Clk**:  Slows down the clock speed.<br>
**Nanoprocessor**:  Executes assembly instructions and manages flags.<br>
**LUT_7seg**:  ROM module storing values for the seven-segment display.<br>

## Hardware Configuration

1. Reset Button (U18): Middle button on the board used for system reset.<br>
2. LEDs (V19, U19, E19, U16): Display the value of Reg_7_LED, with V19 representing the Most Significant Digit (MSD).
3. Seven-Segment Display Ports (W7, W6, U8, V8, U5, V5, U7): Represent the seven bits of the display.
4. Seven-Segment Display Anode (U2, U4, V4, W4): Anode pins for the seven-segment display.
5. Flag Indicators (P1, L1): P1 for overflow and L1 for zero flags of the Nanoprocessor.

## Assembly Program

MOVI R7,0      ; R7 <- 0 <br>
MOVI R1,1      ; R1 <- 1 <br>
MOVI R2,2      ; R2 <- 2 <br>
MOVI R3,3      ; R3 <- 3 <br>
ADD R7,R1      ; R7 <- R7+R1 <br>
ADD R7,R2      ; R7 <- R7+R2 <br>
ADD R7,R3      ; R7 <- R7+R3 <br>
JZR R0,7       ; if R0 = 0 jump to line 7 <br>

## Machine Code

"101110000000"  -- mov R7,0 <br>
"100010000001"  -- mov R1,1 <br>
"100100000010"  -- mov R2,2 <br>
"100110000011"  -- mov R3,3 <br>
"001110010000"  -- add R7,R1 <br>
"001110100000"  -- add R7,R2 <br>
"001110110000"  -- add R7,R3 <br>
"110000010111"  -- jzr R0,7 <br>

## How to Use
Load the bitstream onto the board.<br>
Press the reset button (U18) to initiate the sequence of displaying numbers.

[Live Demostration](https://drive.google.com/file/d/1TIiEV-3udd0xTYGc6TCPPPQpdUJi8NV6/view?usp=sharing)
