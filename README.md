# TinyRV1 FPGA System

Verilog RTL design and verification of a TinyRV1 processor system and custom hardware accelerator.

## Overview

This project was developed as part of Cornell University's ECE 2300: Digital Logic and Computer Organization. The project involved designing, implementing, and verifying digital hardware components in Verilog, progressing from fundamental combinational and sequential logic to processor-level system design.

The project culminated in a TinyRV1 processor-based system integrating custom RTL components, memory-bus control, and a hardware accumulation accelerator.

## Key Contributions

- Designed control and datapath logic for a custom accumulation hardware accelerator.
- Implemented and debugged processor components including a 32-bit ALU, register file, and memory-bus control logic.
- Developed directed Verilog tests for arithmetic, memory, branch, jump, and multiply instructions.
- Designed and verified sequential digital systems including counters, finite-state-machine controllers, and multi-note audio playback logic.
- Used simulation and iterative RTL debugging to verify functional correctness across individual modules and integrated systems.

## System Architecture

The custom accumulation accelerator is organized into separate control and datapath modules and interfaces with the processor system through a memory interface.

```text
              +----------------------+
              |     TinyRV1 System   |
              +----------+-----------+
                         |
                         | Memory Interface
                         v
              +----------------------+
              |  Accumulation Xcel   |
              |                      |
              |  +----------------+  |
              |  | Control Logic  |  |
              |  +-------+--------+  |
              |          |           |
              |  +-------v--------+  |
              |  |    Datapath    |  |
              |  |                |  |
              |  | Size Register  |  |
              |  | Index Counter  |  |
              |  | Addr Counter   |  |
              |  | Sum Register   |  |
              |  +-------+--------+  |
              +----------|-----------+
                         |
                         | mem_addr / mem_rdata
                         v
                    +---------+
                    | Memory  |
                    +---------+
```

## Verification

The design was verified using directed Verilog testbenches at both the module and processor-instruction level.

Testing included:

- ALU arithmetic and logical operations
- Register-file behavior
- Load and store instructions
- Branch and jump instructions
- Multiply operations
- Accelerator control and datapath behavior
- Integrated processor functionality

The project used iterative simulation and RTL debugging to identify and correct control, datapath, and timing-related logic errors.

## Technologies

**HDL:** Verilog  
**Hardware:** FPGA, Digital Logic  
**Design:** RTL, Datapath & Control, Finite State Machines, Processor Systems  
**Verification:** Verilog Testbenches, Directed Testing
