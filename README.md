# ALU Modules Documentation

Name : Kesheng Wang

Netid: kw457

This repository contains Verilog modules for various arithmetic and logic operations in an Arithmetic Logic Unit (ALU). Below is a detailed explanation of each module and its functionality.

## Overview

The ALU performs operations such as addition, subtraction, logical AND, OR, shift left logical (SLL), and shift right arithmetic (SRA). It also provides flags for conditions like overflow, inequality, and less-than comparisons.

## Module Descriptions

### 1. `alu.v`

This is the top-level module that integrates all the operations.

- **Inputs:**
  - `data_operandA`: 32-bit input operand.
  - `data_operandB`: 32-bit input operand.
  - `ctrl_ALUopcode`: 5-bit control signal to select the operation.
  - `ctrl_shiftamt`: 5-bit control signal for shift amount.

- **Outputs:**
  - `data_result`: 32-bit result of the ALU operation.
  - `isNotEqual`: Flag indicating if the inputs are not equal.
  - `isLessThan`: Flag indicating if `data_operandA` is less than `data_operandB`.
  - `overflow`: Flag indicating arithmetic overflow.

### 2. `alu_adder.v`

Performs addition on two 32-bit operands.

- **Outputs:**
  - `res`: Result of the addition.
  - `overflow`: Indicates if an overflow occurred.

### 3. `alu_sub.v`

Performs subtraction and sets flags for inequality and less-than conditions.

- **Outputs:**
  - `res`: Result of the subtraction.
  - `overflow`: Indicates if an overflow occurred.
  - `isNotEqual`: Indicates if the operands are not equal.
  - `isLessThan`: Indicates if `data_operandA` is less than `data_operandB`.

### 4. `alu_and.v`

Performs a bitwise AND operation on two 32-bit operands.

### 5. `alu_or.v`

Performs a bitwise OR operation on two 32-bit operands.

### 6. `alu_sll.v`

Performs a shift left logical operation.

- **Inputs:**
  - `ctrl_shiftamt`: Determines the number of positions to shift.

### 7. `alu_sra.v`

Performs a shift right arithmetic operation, preserving the sign bit.

- **Inputs:**
  - `ctrl_shiftamt`: Determines the number of positions to shift.

### Helper Modules

- **`mux2to1`, `mux4to1`, `mux8to1`:** Multiplexers to select between different inputs based on control signals.
- **`full_adder`:** Basic building block for addition, used in the `RCA` (Ripple Carry Adder) module.
