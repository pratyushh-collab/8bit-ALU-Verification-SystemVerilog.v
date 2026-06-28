# 8-Bit Synthesizable ALU & SystemVerilog Verification Environment

## 📌 Project Overview
This repository contains a fully synthesizable **8-Bit Arithmetic Logic Unit (ALU)** designed using SystemVerilog constructs. It also includes a comprehensive structured Testbench implementing directed test cases driven by strict parameters mapping to verify the logical correctness of the RTL.

This project demonstrates strong foundational skills in digital design, compilation sanity checking, and industry-standard verification practices essential for an aspiring **Design Verification (DV) Engineer** internship selection.

---

## 🛠️ Architecture & Specifications

### 1. Supported Operations
The ALU decodes a 2-bit operation selection identifier (`alu_op`) to execute the following processes:

| Operation Code (`alu_op`) | Abstract Operator Name | Functional Logic Behavior |
| :---: | :---: | :--- |
| `2'b00` | `A` (ADD) | 8-bit Addition with explicit `carry_out` tracking |
| `2'b01` | `B` (SUB) | 8-bit Binary Subtraction |
| `2'b10` | `C` (AND) | Bitwise logical AND operation |
| `2'b11` | `D` (XOR) | Bitwise logical Exclusive OR operation |

### 2. Design Module Highlights (`alu_8bit.sv`)
* Built completely using modern **SystemVerilog `logic` types** to avoid traditional standard `wire/reg` structural mismatch errors.
* Implements explicit `always_comb` block to model exact combinational simulation gates cleanly.
* Includes default initialization hooks to prevent unintended synthesis latches.

### 3. Testbench Architecture (`testbench.sv`)
* **Parameter-Driven Testing:** Uses clean localized parameters mapping (`A, B, C, D`) instead of hardcoded decimal numbers to simulate realistic operational decoding.
* **Bounded Width Checking:** Prevents out-of-bound overflow issues by directly matching target 2-bit variables.
* **Execution Logging:** Uses active `$monitor` loops capturing real-time simulation tracking displayed in decimal formats (`%0d`).

---

## 📂 File Directory Structure
```text
├── alu_8bit.sv       # Synthesizable RTL Design Module
├── testbench.sv      # Directed Testbench Environment
├── waveform.png      # Generated simulation waveform screenshot
└── README.md         # Documentation Report (This file)
