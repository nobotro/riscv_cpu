## fpga_riscv_cpu
This repository contains an extremely simple implementation of the RV32I ISA. The project is entirely academic, it does not aim to be competitive against complex implementations. The rationale behind it was basically learning about RISC-V, the ISA, and processor design in general. If you want to deploy a RISC-V core, [I strongly recommend using a fully-featured and tested core instead.](https://github.com/riscv/riscv-wiki/wiki/RISC-V-Cores-and-SoCs)  

## Current Design
- Entirely written in Verilog.
- Every opcode need one clock cycle to execute, except memory operations(store/load).
- Used 1 port block ram ip for memory inteface
- Not designed with multiple RISC-V harts .
- The privileged ISA is **not** implemented.
- FENCE, FENCE.I and CSR instructions are not implemented.
 
## User Guide
- "whole quartus project" directory contains Quartus 18.1 lite project file.
- "extra" directory contains utils to compile c program rom and generate memory configuration ".mif" file from it.<br/>
	all.sh is main tool which make all stuffs(compile c code,generate mif file)
- led2.c is rom which function is to write number from 0 to 15 in memory address 32.
  32 is memory mapped io address,which is used to control leds and 7 segment display
- rom.mif file is already generated memory configuration file from led2.c

## Soc Demonstration
https://www.youtube.com/watch?v=oh5zmDeH0jg

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=kevlishvilimisha1@gmail.com&lc=US&item_name=Tm8gbWF0dGVyIHdoYXQgcGVvcGxlIHRlbGwgeW91LCB3b3JkcyBhbmQgaWRlYXMgY2FuIGNoYW5nZSB0aGUgd29ybGQ=&no_note=0&cn=&currency_code=USD&bn=PP-DonationsBF:btn_donateCC_LG.gif:NonHosted)
