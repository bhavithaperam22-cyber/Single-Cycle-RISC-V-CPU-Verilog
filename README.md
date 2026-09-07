# Single-Cycle RISC-V CPU | Verilog HDL

## Overview

This project implements a **single-cycle RISC-V CPU** using Verilog HDL. The processor follows a modular RTL architecture consisting of a controller, datapath, register file, arithmetic logic unit, immediate generation logic, instruction memory, and data memory.

The design executes instructions within a single clock cycle by coordinating instruction decoding, register operations, ALU execution, memory access, and program counter updates through the controller and datapath.

The project also includes a Verilog testbench for functional simulation and verification of processor operation.

---

## Features

- Single-cycle processor architecture
- Verilog HDL RTL implementation
- Modular controller and datapath design
- RISC-V instruction execution
- Arithmetic and logical operations
- Register file implementation
- Immediate value generation
- Program counter control
- Branch and jump control
- Instruction memory interface
- Data memory interface
- Memory read and write operations
- Simulation-based functional verification

---

## Architecture

The processor is organized into two major functional sections:

### Controller

The controller decodes the instruction and generates the required control signals for processor operation.

Control logic is responsible for:

- Instruction decoding
- ALU operation selection
- Register write control
- ALU source selection
- Result selection
- Memory write control
- Branch control
- Jump control
- Immediate format selection
- Program counter control

### Datapath

The datapath performs the actual data processing operations of the processor.

It includes:

- Program Counter
- Instruction processing
- Register File
- Immediate Extension Unit
- Arithmetic Logic Unit
- Multiplexers
- Branch target calculation
- Result selection logic
- Memory interface signals

---

## Project Modules

### `riscv_cpu.v`

Main processor module that integrates the controller and datapath.

### `controller.v`

Generates processor control signals based on instruction fields and processor status signals.

### `datapath.v`

Implements the primary data flow of the processor including register access, ALU operations, program counter updates, memory addressing, and result selection.

### `main_decoder.v`

Decodes instruction opcodes and generates high-level processor control signals.

### `alu_decoder.v`

Generates ALU control signals based on instruction function fields.

### `alu.v`

Performs arithmetic and logical operations.

### `reg_file.v`

Implements the processor register file with register read and write functionality.

### `imm_extend.v`

Generates immediate values from the instruction based on the required instruction format.

### `instr_mem.v`

Implements instruction memory and loads instructions using `$readmemh`.

### `data_mem.v`

Implements data memory with:

- Combinational read operation
- Synchronous write operation

### Supporting Modules

The design also includes supporting RTL modules such as:

- Adders
- Multiplexers
- Reset logic
- Top-level integration modules

---

## Verification

The project includes a dedicated Verilog testbench for simulation-based verification.

The testbench initializes the processor, generates the clock and reset signals, and monitors processor memory write operations.

The functional verification checks for the expected processor output:

```text
Data Address = 100
Write Data   = 25
