# 8-Bit CMOS ALU – Full Custom VLSI Design (Transistor-Level)
Physical VLSI Design of an 8-bit Arithmetic Logic Unit with Extended Opcode Set
Author: Betül Atalay

📌 Project Overview

In this project, a full-custom CMOS-based 8-bit Arithmetic Logic Unit (ALU) was designed and verified at the transistor level using Electric VLSI for schematic/layout and LTspice for circuit-level simulation.

The ALU is controlled by a 4-bit opcode and was specified to support 16 different operations. Out of these, 15 operations were successfully implemented and fully verified. The only excluded operation is multiplication, which was intentionally omitted due to its significantly higher structural complexity and time constraints.

All circuits were implemented as true transistor-level CMOS designs, not using any HDL or behavioral models.

🧱 Design Methodology

The entire project follows a fully modular and hierarchical design approach:
Each function was first designed as a 1-bit building block
Then scaled to an 8-bit version

Each block includes:
✅ Transistor-level schematic
✅ Physical layout
✅ Simulation testbench

Finally, the 8-bit ALU was constructed by combining all 8-bit sub-blocks using a hierarchical multiplexer-based selection network.
This methodology significantly improved:
Debuggability
Reusability
Layout consistency
Verification reliability

⚙️ Supported Operations (Opcode Set)

The ALU is controlled by a 4-bit opcode and supports the following operations:

Opcode	Operation	Description
0000	A + B	Addition
0001	A − B	Subtraction
0010	A & B	Bitwise AND
0011	A | B	Bitwise OR
0100	A ^ B	Bitwise XOR
0101	~A	Bitwise NOT
0110	A << 1	Logical left shift
0111	A >> 1	Logical right shift
1000	A × B	❌ Not implemented
1001	A == B	Equality check
1010	A > B	Greater than
1011	A < B	Less than
1100	A NAND B	Bitwise NAND
1101	A NOR B	Bitwise NOR
1110	A <<< 1	Arithmetic left shift
1111	A >>> 1	Arithmetic right shift

⚠️ Multiplication was excluded due to time constraints and high hardware complexity.

🧩 Implemented Submodules

Each of the following has:

✔ Transistor-level schematic
✔ Physical layout
✔ LTspice simulation

Inverter
<img width="1140" height="284" alt="image" src="https://github.com/user-attachments/assets/2454dbac-d28d-4baa-8edf-33ebc2356c00" />
<img width="1154" height="191" alt="image" src="https://github.com/user-attachments/assets/97977758-620c-4d3a-a4e8-f4805542a416" />

NAND, NOR, XOR

Half Adder, Full Adder

8-bit Adder

8-bit Subtractor

Zero Flag Generator

Comparator Logic

Logical Shifters

Arithmetic Shifters

2:1, 4:1, 16:1 MUX (Transmission Gate based)

🏗️ Top-Level Integration Status

✔ Full top-level ALU schematic is complete and verified

🛠️ Tools Used

Electric VLSI → Schematic + Layout

LTspice → Transistor-level simulation
