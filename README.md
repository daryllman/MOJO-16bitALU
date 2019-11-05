# MOJO - 16bit Arithmetic Logic Unit (ALU) implementation with Lucid
#### Web Virtual Reality (WebVR) Experience built with A-frame


## Getting started
To install: 
```
git clone https://github.com/daryllman/MOJO-16bitALU.git
```
1. Open lucid folder on your MOJO IDE by opening ALUproject.mojo
2. Build project 
3. Connect your MOJO and upload to flash memory

## How does our ALU work
-  ALU module is built with separate function modules created (ADDER, BOOLE, CMP, and SHIFTER) which contains the logic for different arithmetic operations 
   * ALU Inputs: A[15:0], B[15:0], ALUFN[5:0]
   * ALU Output: result[15:0], Z t(true if all result[15:0] are 0), V(true if there is overflow), N(true if result is negative)
- The function modules are selected based on specific ALUFN[5:0] being input into the ALU unit and output the result accordingly <br/>
- The ALU has 3 modes: INITIAL (acts like a home page), AUTO MODE and MANUAL MODE
- When MOJO device is on, the device is at INITIAL state, where you can trigger to enter AUTO or MANUAL mode <br/>
- For MANUAL MODE:
   * To ENTER MANUAL: flip the most left switch io_dip[23] up
   * Enter your ALUFN[5:0] inputs to io_dip[21:16] buttons to select which arithmetic operation you want.
   * Enter your A values throguh io_dip_[15:0] buttons and save them by pressing button[0] - top button
   * Enter your B values throguh io_dip_[15:0] buttons and save them by pressing button[1] - center button
   * When OK, press button[2] - bottom button - to save the ALUFN inputs and calculate the result
   * This will display the results on io_led[15:0] & Z V N outputs on the io_seg display, as well as your chosen ALUFN inputs on io_led[21:16]
   * To CLEAR and start again, press button[3] - Left button <br/>
- For AUTO MODE:
   * To ENTER AUTO: At INITIAL mode (when io_dip[23] is 0), press button[4] - right button
   * This will trigger the start of the first test case and loop on to the last, before returning to INITIAL mode.
   * For each Test Case:
1. io_seg will show "1___": this number indicates which test case it is at. ('1' refers to the first one, which is adder-addition). At the same time, io_led[21:16] will show the alufn inputs
2. io_seg will show "___A": The chosen A inputs will display at io_led[15:0]
3. io_seg will show "___B": The chosen B inputs will display at io_led[15:0]
4. io_seg will show "PASS" or "FAIL": pass/fail will depend on the comparison between the correct expected result & the result calculated by the ALU. At the same time, io_led[15:0] will display the results & io[18:16] will show the Z,V,N outputs 


## Members
### Group 2-4
- Daryll Wong - SUTD Sophomore | Information Systems Technology & Design (ISTD)
- Sheikh Salim - SUTD Sophomore | Information Systems Technology & Design (ISTD)
- Evangeline Lim - SUTD Sophomore | Information Systems Technology & Design (ISTD)
- Gabriel Koh - SUTD Sophomore | Information Systems Technology & Design (ISTD)
- Iman Heizer Pua - SUTD Sophomore | Information Systems Technology & Design (ISTD)

## Credits
* [Lucid](https://alchitry.com/pages/lucid-fpga-tutorials) - Lucid tutorials 
