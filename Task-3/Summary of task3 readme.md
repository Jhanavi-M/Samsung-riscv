HERE IS A LIST OF 15 UNIQUE INSTRUCTION SET ALONG WITH 32 BIT REPRESENTATION FOR EACH.


R-Type (Register-Register Instructions)

1.Instruction: mul a5, a4, a5

Operation: Multiply the values in registers a4 and a5, and store the result in register a5.
Opcode: 0110011 (R-Type for arithmetic operations)
Funct3: 000 (For mul operation)
rd (Destination register): a5 (register 5 in decimal)
rs1 (Source register 1): a4 (register 4 in decimal)
rs2 (Source register 2): a5 (register 5 in decimal)
Immediate: Not used in this instruction (R-type format)

Full Binary Instruction:
0000 0010 1111 0111 0000 0111 1011 0011

32-bit Instruction Pattern:
funct7        rs2        rs1        funct3    rd        opcode
0000000       00101      00100      000       00101     0110011

Final Hexadecimal Instruction:
0x02F707B3
This instruction mul a5, a4, a5 multiplies the values in registers a4 and a5, storing the result in register a5. The machine code for this instruction is 0x02F707B3.


2.Instruction: mv a0, a5
Operation: Move the value in register a5 to register a0.
Opcode: 0110011 (R-Type for register-register operations)
Funct3: 000 (For add operation, used here in mv)
rd (Destination register): a0 (register 10 in decimal)
rs1 (Source register 1): a5 (register 5 in decimal)
rs2 (Source register 2): Not used (since it's a move operation, effectively copying from rs1 to rd)
Immediate: Not used in this instruction (R-type format)

Full Binary Instruction:
0000 0000 0000 0111 1000 0101 0001 0011

32-bit Instruction Pattern:
funct7        rs2        rs1     funct3    rd        opcode
0000000       00000      00101   000       01010     0110011

Final Hexadecimal Instruction:
0x00078513
This instruction mv a0, a5 copies the value from register a5 into register a0. The machine code for this instruction is 0x00078513.



3.Instruction: sltu a5, a0, a5
Operation: Set register a5 to 1 if the value in register a0 is less than the value in register a5 (unsigned comparison). Otherwise, set register a5 to 0.
Opcode: 0110011 (R-Type for arithmetic and comparison instructions)
Funct3: 011 (For sltu operation)
rd (Destination register): a5 (register 5 in decimal)
rs1 (Source register 1): a0 (register 10 in decimal)
rs2 (Source register 2): a5 (register 5 in decimal)
Immediate: Not used in this instruction (R-type format)

Full Binary Instruction:
0000000 00101 01010 011 00101 0110011

32-bit Instruction Pattern:
funct7        rs2        rs1     funct3    rd        opcode
0000000       00101      01010   011       00101     0110011

Final Hexadecimal Instruction:
0x00030333
This instruction sltu a5, a0, a5 performs an unsigned comparison between the values in registers a0 and a5. If a0 is less than a5, it sets a5 to 1; otherwise, it sets a5 to 0. The machine code for this instruction is 0x00030333.








I-Type(Immediate Instruction)


1.Instruction: li a5, 1
Operation: Load the immediate value 1 into register a5.
Opcode: 0010011 (I-Type for addi)
Funct3: 000 (For addi operation)
rd (Destination register): a5 (register 5 in decimal)
rs1 (Source register): x0 (register 0, always 0)
Immediate: 1 (Value being loaded into a5)

Full Binary Instruction :
0000 0100 0111 1000 0101 0000 0000 0000

32 bit Instruction Pattern:
imm[11:0]	     rs1   funct3	     rd	        opcode
000001000111	 10000	 000	     00101	    0010011

Final Hexadecimal Instruction:
0x0004785
This instruction loads the immediate value 1 into register a5.



2. Instruction: addi sp, sp, -48
Operation: Add the immediate value -48 to register sp → sp = sp - 48
Opcode: 0010011 (I-Type for addi)
Funct3: 000 (For addi operation)
rd (Destination register): sp (register 2 in decimal)
rs1 (Source register): sp (register 2 in decimal)
Immediate: -48 (Value being added to sp)

Full binary Instruction:
0000 0111 0001 0111 1001 0000 0000 0000

32-bit Instruction Pattern:
imm[11:0]	     rs1   funct3	     rd	        opcode
000001110001	11101	  000	      11101	      0010011

Final Hexadecimal Instruction:
0x71790000
This instruction subtracts 48 from the stack pointer (sp).


3.Instruction: lw a5, -20(s0)
Operation: Load the 32-bit value from memory at the address s0 - 20 into register a5.
Opcode: 0000011 (I-Type for load instructions)
Funct3: 010 (For lw operation)
rd (Destination register): a5 (register 5 in decimal)
rs1 (Source register): s0 (register 8 in decimal)
Immediate: -20 (The offset being added to s0)

Full Binary Instruction:
1111 1110 1100 0100 0010 0111 1000 0011

32-bit Instruction Pattern:
imm[11:0]        rs1     funct3    rd        opcode
111111111100      01000   010       00101     0000011

Final Hexadecimal Instruction:
0xFEC42783
This instruction lw a5, -20(s0) loads a 32-bit word from memory at the address s0 - 20 into register a5. The machine code for this instruction is 0xFEC42783.


4.Instruction: ld a4, -32(s0)
Operation: Load the 64-bit value from memory at the address s0 - 32 into register a4.
Opcode: 0000011 (I-Type for load instructions)
Funct3: 011 (For ld operation)
rd (Destination register): a4 (register 4 in decimal)
rs1 (Source register): s0 (register 8 in decimal)
Immediate: -32 (The offset being added to s0)

Full Binary Instruction:
1111 1110 0000 0100 0011 0111 0000 0011

32-bit Instruction Pattern:
imm[11:0]        rs1     funct3    rd        opcode
111111110000      01000   011       00100     0000011

Final Hexadecimal Instruction:
0xFE043703
This instruction ld a4, -32(s0) loads a 64-bit doubleword from memory at the address s0 - 32 into register a4. The machine code for this instruction is 0xFE043703.




5.Instruction: jalr ra, 16(sp)
Operation: Jump and link to the address 16 + sp and store the return address in register ra.
Opcode: 1100111 (I-Type for jalr instruction)
Funct3: 000 (For jalr operation)
rd (Destination register): ra (register 1 in decimal)
rs1 (Source register): sp (register 2 in decimal)
Immediate: 16 (The offset being added to sp)

Full Binary Instruction:
0000 0000 0000 0000 0000 1000 1110 0111

32-bit Instruction Pattern:
imm[11:0]        rs1     funct3    rd        opcode
000000000000      00010   000       00001     1100111

Final Hexadecimal Instruction:
0x000080E7
This instruction jalr ra, 16(sp) jumps to the address 16 + sp and stores the return address (the address of the next instruction) in register ra. The machine code for this instruction is 0x000080E7.



S-Type(Store Instructions)


1.Instruction: sd ra, 40(sp)
Operation: Store the 64-bit value in register ra (x1) into memory at the address 40 + sp.
Opcode: 0100011 (S-Type for store instructions)
Funct3: 011 (For sd operation)
rs1 (Source register): sp (register 2 in decimal)
rs2 (Source register): ra (register 1 in decimal)
Immediate: 40 (Offset being added to sp)

Full Binary Instruction:
0000 0000 0000 0001 0001 0011 0100 0011


32-bit Instruction Pattern:
imm[11:5]       rs2     rs1     funct3   imm[4:0]     opcode
0000000         00001   00010   011      01000        0100011


Final Hexadecimal Instruction:
0x00012283

This instruction sd ra, 40(sp) stores the value in register ra (x1) into memory at the address 40 + sp. The machine code for this instruction is 0x00012283.



2.Instruction: sw a5, -20(s0)
Operation: Store the 32-bit value from register a5 into memory at the address s0 - 20.
Opcode: 0100011 (S-Type for store instructions)
Funct3: 010 (For sw operation)
rs1 (Source register 1): s0 (register 8 in decimal)
rs2 (Source register 2): a5 (register 5 in decimal)
Immediate: -20 (The offset being added to s0)

Full Binary Instruction:
1111 1110 1111 0100 0010 0110 0011 0011

32-bit Instruction Pattern:
imm[11:5]        rs2     rs1     funct3    imm[4:0]    opcode
1111111          00101   01000   010       10011       0100011

Final Hexadecimal Instruction:
0xFEF42623
This instruction sw a5, -20(s0) stores the contents of register a5 into memory at the address s0 - 20. The machine code for this instruction is 0xFEF42623.






B-Type(Branch Instructions)

1.Instruction: bgez a5, 4e
Operation: Branch if the value in register a5 is greater than or equal to zero. If true, the program will branch to the address PC + 0x4e.
Opcode: 1100011 (B-Type for branch instructions)
Funct3: 001 (For bgez operation)
rs1 (Source register 1): a5 (register 5 in decimal)
rs2 (Source register 2): Not used (for branch instructions)
Immediate: 0x4e (Offset to branch to)

Full Binary Instruction:
0000 0000 0000 0111 1011 1011 0110 0011

32-bit Instruction Pattern:
imm[12]          imm[10:5]    rs1     funct3   imm[4:1]    imm[11]    opcode
0                000000       00101   001      01110       0          1100011

Final Hexadecimal Instruction:
0x0007DB63
This instruction bgez a5, 4e branches to the address PC + 0x4e if the value in register a5 is greater than or equal to zero. The machine code for this instruction is 0x0007DB63.




U-Type(Upper Immediate Instructions)


1.Instruction: lui a5, 0x0
Operation: Load the upper immediate value 0x0 into the upper 20 bits of register a5.
Opcode: 0110111 (LUI type instruction)
Funct3: 000 (For LUI operation)
rd (Destination register): a5 (register 5 in decimal)
rs1 (Source register): Not used (always x0)
Immediate: 0x0 (The immediate value that will be loaded into the upper 20 bits of a5)

Full Binary Instruction:
0000 0000 0000 0000 0000 0000 0101 1011

32-bit Instruction Pattern:
imm[31:12]        rd        funct3        opcode
000000000000      00101     000           0110111

Final Hexadecimal Instruction:
0x000007B7
This instruction lui a5, 0x0 loads the immediate value 0x0 into the upper 20 bits of register a5. The machine code for this instruction is 0x000007B7.



2.Instruction: auipc ra, 0x0
Operation: Add the upper immediate value 0x0 to the current program counter (PC) and store the result in register ra.
Opcode: 0010111 (AUIPC type instruction)
Funct3: 000 (For AUIPC operation)
rd (Destination register): ra (register 1 in decimal)
rs1 (Source register): Not used
Immediate: 0x0 (The immediate value being added to the current PC)

Full Binary Instruction:
0000 0000 0000 0000 0000 0000 0100 1101

32-bit Instruction Pattern:
imm[31:12]        rd        funct3        opcode
000000000000      00001     000           0010111

Final Hexadecimal Instruction:
0x00000097
This instruction auipc ra, 0x0 adds the immediate value 0x0 to the current program counter (PC) and stores the result in register ra. The machine code for this instruction is 0x00000097.






J-Type(Jump Instruction)

1.Instruction: j 70<.L4>
Operation: Jump to the address 70 (offset from the current program counter).
Opcode: 1101111 (J-Type for unconditional jump instructions)
Funct3: 000 (For jal operation)
rd (Destination register): x0 (register 0 in decimal, as no return address is needed for this jump)
rs1 (Source register): Not used
Immediate: 70 (The offset from the current PC)

Full Binary Instruction:
1010 0011 0001 0000 0001 1000 0011 0001

32-bit Instruction Pattern:
imm[20]    imm[10:1]    imm[11]    imm[19:12]    rd    opcode
1          0100000001    0          0000001000     00000 1101111

Final Hexadecimal Instruction:
0xA831
This instruction j 70<.L4> is an unconditional jump instruction that jumps to the address PC + 70. The machine code for this instruction is 0xA831.


Other instruction

1.Instruction: addi s0, sp, 48
Operation: Add the immediate value 48 to the value in register sp (stack pointer) and store the result in register s0.
Opcode: 0010011 (I-Type for immediate arithmetic instructions)
Funct3: 000 (For addi operation)
rd (Destination register): s0 (register 8 in decimal)
rs1 (Source register): sp (register 2 in decimal)
Immediate: 48 (The value being added to sp)

Full Binary Instruction:
0000 0000 0000 0010 0001 0010 1000 1011

32-bit Instruction Pattern:
imm[11:0]        rs1     funct3    rd        opcode
000000000100      00010   000       01000     0010011

Final Hexadecimal Instruction:
0x0002A023
This instruction addi s0, sp, 48 adds the immediate value 48 to the value in register sp and stores the result in register s0. The machine code for this instruction is 0x0002A023.

















