<h1 align="center">⚡ 8-Bit CMOS ALU – Full Custom VLSI Design</h1>

<p align="center">
Transistor-Level • Full Custom • Electric VLSI • LTspice
</p>

---

## 📌 Project Overview

This project presents the **physical VLSI design of an 8-bit Arithmetic Logic Unit (ALU)** implemented entirely at the **transistor level using CMOS logic**.

The ALU was designed and verified using:

- 🧩 **Electric VLSI** → schematic + physical layout  
- 🔬 **LTspice** → transistor-level simulation  

The ALU is controlled by a **4-bit opcode** supporting **16 operations**.

✅ **15 operations fully implemented and verified**  
⚠️ Multiplication intentionally excluded due to structural complexity and time constraints.

All circuits are true **transistor-level CMOS implementations**, with **no HDL or behavioral modeling**.

---

# 🧱 Design Methodology

The project follows a **modular and hierarchical full-custom design approach**:

1️⃣ Each function first designed as a **1-bit building block**  
2️⃣ Then scaled to **8-bit implementations**

Each module includes:

✔ Transistor-level schematic  
✔ Physical layout  
✔ LTspice simulation testbench  

Final integration was done using a **hierarchical multiplexer-based selection network**.

### ✔ Benefits of this methodology

- Debuggability  
- Reusability  
- Layout consistency  
- Verification reliability  

---

# ⚙️ Supported Operations

The ALU is controlled by a 4-bit opcode.

<img src="https://github.com/user-attachments/assets/3b46fd19-d4d1-40a9-a673-e6754df035a3" width="700"/>

⚠️ Multiplication excluded due to hardware complexity.

---

# 🧩 Implemented Submodules

Each block includes schematic, layout, and simulation verification.

---

## 🔹 Logic Units

### 8-Bit Inverter
<img src="https://github.com/user-attachments/assets/2454dbac-d28d-4baa-8edf-33ebc2356c00" width="600"/>
<img src="https://github.com/user-attachments/assets/97977758-620c-4d3a-a4e8-f4805542a416" width="600"/>

---

### 8-Bit NAND
<img src="https://github.com/user-attachments/assets/df4777ec-8604-4092-8dda-b4452f93a2d5" width="600"/>
<img src="https://github.com/user-attachments/assets/6fe6d5ff-2469-4219-a42f-51b049569bf6" width="600"/>

---

### 8-Bit NOR
<img src="https://github.com/user-attachments/assets/fd68d957-6d93-4c33-b33e-0fac9c5bdd20" width="600"/>
<img src="https://github.com/user-attachments/assets/7cf85aee-cd2d-444b-9c6e-eadf9bc17108" width="600"/>

---

### 8-Bit AND
<img src="https://github.com/user-attachments/assets/aeffa648-8dd1-48f1-b0ed-e2d58bfe2a28" width="600"/>

---

### 8-Bit OR
<img src="https://github.com/user-attachments/assets/71f3175a-45db-48f9-af27-feda701f6c6d" width="600"/>

---

### 8-Bit XOR
<img src="https://github.com/user-attachments/assets/06b2e31c-313f-4ed8-acad-78f124d9d74e" width="600"/>

---

## ➕ Arithmetic Units

### Half Adder
<img src="https://github.com/user-attachments/assets/78497acf-754b-4c90-8e22-40244eee57ac" width="600"/>
<img src="https://github.com/user-attachments/assets/ca8532b7-9f2c-482a-8486-f299ae6eb863" width="600"/>

---

### Full Adder
<img src="https://github.com/user-attachments/assets/09be5a14-b9d0-48d1-81ac-36a5dc2ae004" width="600"/>
<img src="https://github.com/user-attachments/assets/cffb1809-e41f-4fda-864a-fc94e3b4e630" width="600"/>

---

### 8-bit Adder
<img src="https://github.com/user-attachments/assets/64a9b35f-ba48-46b5-88a0-43872d0b1b1e" width="700"/>

---

## ➖ Subtractor & Comparator

A shared arithmetic path enables:

- A − B  
- A == B  
- A > B  
- A < B  

using flag logic.

<img src="https://github.com/user-attachments/assets/b75942cb-632c-4bbe-b69a-b59e5d5184ea" width="600"/>
<img src="https://github.com/user-attachments/assets/e049605a-2685-4c5c-839a-ae6e9e7717f2" width="600"/>

---

## 🔁 Shifters

### Logical Left
<img src="https://github.com/user-attachments/assets/985ce9d4-7112-4723-b6e2-cf82a828965c" width="600"/>
<img src="https://github.com/user-attachments/assets/b535d6cd-d716-43b5-ae99-de764fe15e9f" width="600"/>

### Logical Right
<img src="https://github.com/user-attachments/assets/7f0b67e0-88ac-4c1c-baec-4976b44d31de" width="600"/>
<img src="https://github.com/user-attachments/assets/9f9fe9eb-eb2b-4769-9018-436f4749709c" width="600"/>

### Arithmetic Left
<img src="https://github.com/user-attachments/assets/3168cd8b-e67c-4891-8baf-b926a732c79f" width="600"/>

### Arithmetic Right
<img src="https://github.com/user-attachments/assets/e3d2a700-4db2-4535-8b89-9d48f7f13c44" width="600"/>

---

# 🔀 16:1 MUX (Transmission-Gate Based)

Instead of building a flat 16:1 MUX:

2:1 → 4:1 → 16:1 hierarchy was used.

✔ Reduced design risk  
✔ Easier verification  
✔ Layout reuse  

Transmission-gate-based design:

✔ Lower transistor count  
✔ Reduced routing complexity  
✔ Significant area savings

<img src="https://github.com/user-attachments/assets/7a70d78b-dab0-49bc-9f59-52ae0b98efb5" width="350"/>
<img src="https://github.com/user-attachments/assets/c2cc4757-30b6-4c26-8377-4ad07fe36630" width="500"/>

---

# 🏗️ Top-Level ALU

✔ Fully complete and verified

<img src="https://github.com/user-attachments/assets/a8f3ad4f-dbf5-40d6-9dbc-e10ccfb20b6f" width="600"/>

---

# 🏁 Integration Status

<img src="https://github.com/user-attachments/assets/63aacb5f-2c5d-453a-9889-834cfdc028cb" width="700"/>

---

# 🛠️ Tools Used

- **Electric VLSI** → schematic + layout  
- **LTspice** → transistor-level simulation  

---

# 👩‍💻 Author

**Betül Atalay**  
Electrical & Electronics Engineering

---

# 📜 License

Shared for **educational and academic purposes**.


⭐ If you find this project interesting, consider starring the repo!

