# SPI Slave with Single-Port RAM (Verilog)

## Overview
This project implements an **SPI Slave** module in Verilog that communicates with a **single-port RAM (SPR)**.  
The design enables an SPI Master to perform **read and write operations** to memory through a simple protocol:

- **Addressing phase**: SPI Master sends the target address.  
- **Write phase**: Data is written to RAM at the selected address.  
- **Read phase**: Data stored at the address is read out and sent back over SPI.  

A complete **testbench (`spiwrapper_tb`)** simulates SPI Master behavior to verify all transactions: write address, write data, read address, and read data.  

---

## Features
- **SPI Slave (FSM-based)** with support for:
  - Write operations  
  - Read address latching  
  - Data read-back from memory  
- **Single-Port RAM** (`spr_sync`) with configurable depth and address size.  
- **Wrapper module** (`spi_wrapper`) connecting SPI logic with RAM.  
- **Testbench** simulating SPI Master transactions (read/write).  
- Memory preloading via `$readmemh("mem.dat", DUT.RAM.mem)` for simulation.  

---

## Tools & Requirements
- **Language**: Verilog HDL  
- **Simulation**: QuestaSim, Vivado simulator  
- **Synthesis**: FPGA-compatible (Xilinx/Intel FPGAs)  
- Testbench-driven simulation (no external SPI Master required).  


