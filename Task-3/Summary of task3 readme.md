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

















