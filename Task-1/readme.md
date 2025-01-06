# Sum from 1 to N - C and RISC-V Analysis

This repository contains a simple C program to compute the sum of numbers from 1 to N, along with an analysis of the generated RISC-V assembly code when compiled with different optimization levels.

## Description

The program demonstrates:
- A simple algorithm for summing integers from 1 to N.
- Observations on the compiled RISC-V code with optimization levels `-O1` and `-Ofast`.

### C Code
The C program computes the sum using the formula:

### RISC-V Code Observations
The compiled RISC-V code was analyzed using `objdump`. Key findings are:
1. **Instruction Count in the `main` Function:**
   - **`-O1`**: 15 instructions.
   - **`-Ofast`**: 12 instructions.

2. **Instruction Addressing:**
   - Each instruction is located at addresses separated by 4 bytes, reflecting the fixed instruction length of the RISC-V architecture.

## Files in this Repository
-  The C program to compute the sum.
- `README.md`: This file.
-  The RISC-V assembly dump for the `-O1` optimization level.
-  The RISC-V assembly dump for the `-Ofast` optimization level.

## Steps to Reproduce
1. Compile the C code to RISC-V assembly using GCC
