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
✅Debuggability
✅Reusability
✅Layout consistency
✅Verification reliability

⚙️ Supported Operations (Opcode Set)

The ALU is controlled by a 4-bit opcode and supports the following operations:

<img width="1600" height="1009" alt="Code_Generated_Image (1)" src="https://github.com/user-attachments/assets/3b46fd19-d4d1-40a9-a673-e6754df035a3" />

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

Logical Shifters : Left 
<img width="1247" height="590" alt="image" src="https://github.com/user-attachments/assets/985ce9d4-7112-4723-b6e2-cf82a828965c" />
<img width="1282" height="506" alt="image" src="https://github.com/user-attachments/assets/b535d6cd-d716-43b5-ae99-de764fe15e9f" />

Logical Shifters : Right
<img width="1362" height="640" alt="image" src="https://github.com/user-attachments/assets/7f0b67e0-88ac-4c1c-baec-4976b44d31de" />
<img width="1053" height="505" alt="image" src="https://github.com/user-attachments/assets/9f9fe9eb-eb2b-4769-9018-436f4749709c" />

Arithmetic Shifters : Left
<img width="1259" height="584" alt="image" src="https://github.com/user-attachments/assets/3168cd8b-e67c-4891-8baf-b926a732c79f" />

Arithmetic Shifters : Right
<img width="1373" height="634" alt="image" src="https://github.com/user-attachments/assets/e3d2a700-4db2-4535-8b89-9d48f7f13c44" />

16:1 MUX (Transmission Gate based)
Instead of building a flat 16:1 directly, I first created reusable 2:1 MUX cells, then combined them into 4:1 MUX modules, and finally constructed the 16:1 selection by composing these 4:1 blocks. This modular hierarchy reduced design risk, simplified verification, and allowed layout reuse—each level (2:1 → 4:1 → 16:1) was validated in schematic and simulation before integration into the top-level ALU.
Using transmission-gate-based 2:1 multiplexers instead of conventional CMOS MUXes significantly reduces transistor count and routing complexity, yielding a substantial area advantage in the opcode selection network.
<img width="488" height="605" alt="image" src="https://github.com/user-attachments/assets/7a70d78b-dab0-49bc-9f59-52ae0b98efb5" />
<img width="784" height="562" alt="image" src="https://github.com/user-attachments/assets/c2cc4757-30b6-4c26-8377-4ad07fe36630" />


🏗️ Top-Level Integration Status
<img width="1748" height="809" alt="image" src="https://github.com/user-attachments/assets/63aacb5f-2c5d-453a-9889-834cfdc028cb" />

✔ Full top-level ALU schematic is complete and verified
<img width="881" height="894" alt="image" src="https://github.com/user-attachments/assets/a8f3ad4f-dbf5-40d6-9dbc-e10ccfb20b6f" />

🛠️ Tools Used
Electric VLSI → Schematic + Layout
LTspice → Transistor-level simulation

📜 License
This project is shared for educational and academic purposes.
