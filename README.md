# fsm-ps2-lcd
FSM in SystemVerilog for interfacing PS2 make codes to display on AlteraDE2 LCD screen


## Requirements

You will need the following for using the programming FPGA:

- Altera DE2 Education Board
- Any PS/2 Keyboard OR a USB keyboard and a USB-PS/2 dongle

## What it does:

To be brief a key is pressed on the keyboard sending the make code for a character, if the key is pressed and depressed the breakcode and following makecode is masked so that only the initial make code is sent to the FPGA. Once inside the FPGA it is converted from a PS/2 code to the corresponding LCD code as specified in the .MIF file. The LCD on the DE2 board has a maximum of 16 characters per line and 2 lines, so a register is used to hold the first 16 values and then dumps them onto the LCD all at once.  The left key sets a flag for upper case characters and the right shift sets the flag to low for returning to lowercase characters.

Additional funcitonality has been added so that if the two LCD lines have equal alphanumeric characters regardless of upper or lower case then the leftmost 7 segment display will show a 'D' for detected, otherwise that display will ony be 0.
