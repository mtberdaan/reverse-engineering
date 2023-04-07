# Assembly

## x86

### Registers

- General purpose registers
- Segment registers
- Flag registers
- Instruction pointers

In x86 architecture, each general purpose register has its designated purpose and is stored at WORD size, or 16 bits.

- Accumulator (AX)
- Counter (CX)
- Data (DX)
- Base (BX)
- Stack pointer (SP)
- Base pointer (BP)
- Source index (SI)
- Destination index (DI)

When running code, the system needs to identify where the code is at. The Instruction Pointer (IP) register is the one that contains the memory address where the next assembly instruction to be executed is stored.

System states and logical results of executed code are stored in the FLAGS register. Every bit of the FLAGS register has its own purpose.

All these registers have an "extended" mode for 32-bits. It can be accessed with a prefixed "E" (EAX, ECX, EBX, EDX, ESP, EIP and EFLAGS). The same goes with 64-bit mode, which can be accessed with a prexid "R" (RAX, RBX, RCX, RDX, RSP and RIP).

The memory is devided into sections, the segment registers are used to identify the starting location of these sections;

- Stack segment (SS)
- Code segment (CS)
- Data segment (DS)
- Extra segment (ES)
- F segment (FS)
- G segment (GS)

When a program loads, the operating system maps the executable file to memory.
The code segment contains the executable code. The data segment contains the data bytes, such as constants, strings, and global variables. The stack segment is allocated to contain runtime function variables and other processed data. The extra segment is similar to the data segment, but this space is commonly used to move data between variables. FS and GS point to process and thread information respectively.

### Basic instructions

label/address - mnemonic - operands - ;comments

- label is used to define the location of the instruction line
- mnemonic is a human readable instruction such as MOV, ADD and SUB. Every mnemonic is represented by a byte number or a couple of bytes called an opcode.
- operands are the instruction arguments. read as destination, source. 
- comments 

Assembly language instructions can be categorized as follows:

- copying and accessing data instructions (MOV, LEA, MOVB)
- arithmetic instructions (ADD, SUB, MUL, DIV)
- binary logic instructions (XOR, NOT, SHR, ROL)
- flow control (JMP, CALL, CMP, INT)

MOV instruction is used to move data, either to or from a register or a memory address.
MOV is used to read the value at a given address, while LEA (Load Effective Address) is used to get the address instead.

In addition (ADD) and substraction (SUB) the OF (overflow flag), SF (sign flag) and CF carry flag) flags are affected.

The INC instruction simply adds 1, while DEC substracts 1.

MUL is used for multiplication and DIV for division, in multiplication it is expected that the results will exceed the capacity of the register value, hence the product is stored in AX.

NEG does a two's complement
MOVSX moves a BYTE to WORD or WORD to DWORD, it is more flixible than CBW, CWDE, CWD since it accomodates operands.
CBW converts a BYTE into WORD or WORD into DWORD.
CWDE converst WORD into DWORD
CWD converts WORD into DWORD
IMUL/IDIV this performs MUL and DIV, but accepts operands from other registers or memory.

### Bitwise algebra

NOT
AND
OR
XOR
SHL/SAL
SHR/SAR
ROL
ROR

### Control flow

### Stack manipulation


