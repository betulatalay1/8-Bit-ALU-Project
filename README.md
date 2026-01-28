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

8-Bit Inverter
<img width="1140" height="284" alt="image" src="https://github.com/user-attachments/assets/2454dbac-d28d-4baa-8edf-33ebc2356c00" />
<img width="1154" height="191" alt="image" src="https://github.com/user-attachments/assets/97977758-620c-4d3a-a4e8-f4805542a416" />

8-Bit NAND
<img width="1374" height="269" alt="image" src="https://github.com/user-attachments/assets/df4777ec-8604-4092-8dda-b4452f93a2d5" />
<img width="1353" height="198" alt="image" src="https://github.com/user-attachments/assets/6fe6d5ff-2469-4219-a42f-51b049569bf6" />

8-Bit NOR
<img width="1518" height="329" alt="image" src="https://github.com/user-attachments/assets/fd68d957-6d93-4c33-b33e-0fac9c5bdd20" />
<img width="1357" height="233" alt="image" src="https://github.com/user-attachments/assets/7cf85aee-cd2d-444b-9c6e-eadf9bc17108" />

8-Bit AND
<img width="1427" height="564" alt="image" src="https://github.com/user-attachments/assets/aeffa648-8dd1-48f1-b0ed-e2d58bfe2a28" />

8-Bit OR
<img width="1500" height="688" alt="image" src="https://github.com/user-attachments/assets/71f3175a-45db-48f9-af27-feda701f6c6d" />

8-Bit XOR
<img width="1582" height="634" alt="image" src="https://github.com/user-attachments/assets/06b2e31c-313f-4ed8-acad-78f124d9d74e" />

Half Adder
<img width="960" height="419" alt="image" src="https://github.com/user-attachments/assets/78497acf-754b-4c90-8e22-40244eee57ac" />
<img width="999" height="325" alt="image" src="https://github.com/user-attachments/assets/ca8532b7-9f2c-482a-8486-f299ae6eb863" />

Full Adder
<img width="1179" height="675" alt="image" src="https://github.com/user-attachments/assets/09be5a14-b9d0-48d1-81ac-36a5dc2ae004" />
<img width="1187" height="376" alt="image" src="https://github.com/user-attachments/assets/cffb1809-e41f-4fda-864a-fc94e3b4e630" />

8-bit Adder
<img width="1823" height="456" alt="image" src="https://github.com/user-attachments/assets/64a9b35f-ba48-46b5-88a0-43872d0b1b1e" />

8-bit Subtractor & Comparator:
Subtraction and all comparison operations were consolidated into a single shared arithmetic path: one subtractor simultaneously supports A − B, A == B, A > B, and A < B through flag logic
<img width="1372" height="732" alt="image" src="https://github.com/user-attachments/assets/b75942cb-632c-4bbe-b69a-b59e5d5184ea" />
<img width="835" height="411" alt="image" src="https://github.com/user-attachments/assets/e049605a-2685-4c5c-839a-ae6e9e7717f2" />


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
