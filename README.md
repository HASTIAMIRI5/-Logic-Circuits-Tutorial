# 🔌 Logic Circuits Tutorial

A comprehensive, hands-on guide to learning digital logic circuits from basic gates to sequential systems — with clean code, simulations, and interactive examples in Persian and English.

![Verilog](https://img.shields.io/badge/Verilog-HDL-blue.svg)
![Python](https://img.shields.io/badge/Python-3.9+-green.svg)
![Logisim](https://img.shields.io/badge/Logisim-Evolution-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 📖 About

This repository is a complete, structured curriculum for learning digital logic circuits. Every concept is explained with:

- 📐 Boolean algebra — the math behind every gate
- 🔧 Circuit simulations — build and test in Logisim / Verilog
- 💻 Code implementations — hardware described in Verilog HDL
- 🐍 Python simulators — visualize signals and truth tables
- 📊 Timing diagrams — understand propagation delays and clocking

From a single NAND gate to a full CPU datapath, we build it all step by step.

---

## 📚 Table of Contents

### 🟢 Beginner — Combinational Logic

- 01. Basic Gates (AND, OR, NOT, NAND, NOR, XOR, XNOR) — 📄 🔧
- 02. Boolean Algebra & Simplification — 📄 📓
- 03. Karnaugh Maps (K-Map) — 📄 📓
- 04. Combinational Circuits (MUX, DEMUX, Encoder, Decoder) — 📄 🔧

### 🟡 Intermediate — Arithmetic & Sequential Logic

- 05. Adders & Subtractors (Half/Full, Ripple Carry) — 📄 🔧
- 06. Comparators & ALU Design — 📄 🔧
- 07. Latches & Flip-Flops (SR, D, JK, T) — 📄 🔧
- 08. Registers & Counters — 📄 🔧

### 🔴 Advanced — State Machines & Systems

- 09. Finite State Machines (FSM) — 📄 📓
- 10. Memory Design (RAM, ROM) — 📄 🔧
- 11. Simple CPU Datapath — 📄 📓

### 🏆 Projects

- Digital Clock — 7-segment display + counter + BCD
- Traffic Light Controller — FSM-based intersection controller
- 4-bit Calculator — Full ALU + registers + display
- Simple CPU — 8-bit accumulator-based processor

---

## 🚀 Getting Started

### 1) Clone the repository

```bash
git clone https://github.com/HASTIAMIRI5/-Logic-Circuits-Tutorial.git
cd -Logic-Circuits-Tutorial
```

### 2) Install Python simulators (optional)

```bash
python -m venv venv
source venv/bin/activate       # Linux / macOS
venv\Scripts\activate          # Windows
pip install -r requirements.txt
```

### 3) Install Logisim Evolution

Download from the official releases page and open any `.circ` file:

https://github.com/logisim-evolution/logisim-evolution/releases

### 4) Install Icarus Verilog (for `.v` files)

#### Ubuntu / Debian

```bash
sudo apt install iverilog gtkwave
```

#### macOS

```bash
brew install icarus-verilog gtkwave
```

### ☁️ Run in Google Colab

Python notebooks include “Open in Colab” badges — no installation needed.

---

## 🛠️ Requirements

- Logisim Evolution — visual circuit simulator
- Icarus Verilog + GTKWave — HDL simulation
- Python 3.9+ — for truth tables, K-maps, and plotting
- NumPy, Matplotlib, SymPy

Full list: `requirements.txt`

---

## 📂 Repository Structure

```text
logic-circuits-tutorial/
├── README.md
├── requirements.txt
├── LICENSE
├── .gitignore
├── 01_basic_gates/          # AND, OR, NOT, NAND, NOR, XOR
├── 02_boolean_algebra/      # Laws, identities, simplification
├── 03_kmap/                 # Karnaugh map solver
├── 04_combinational/        # MUX, DEMUX, Encoder, Decoder
├── 05_adders/               # Half/full adders, ripple carry
├── 06_alu/                  # Arithmetic Logic Unit
├── 07_flipflops/            # SR, D, JK, T flip-flops
├── 08_registers/            # Registers, shift registers, counters
├── 09_fsm/                  # State machines
├── 10_memory/               # RAM, ROM
├── 11_cpu/                  # Datapath & control unit
├── 12_projects/             # End-to-end projects
├── diagrams/                # Timing diagrams & schematics
├── utils/                   # Simulation & visualization helpers
└── .github/                 # GitHub configs, workflows, templates
```

---

## 🎯 Learning Path

Follow this order for the best experience:

Basic Gates → Boolean Algebra → K-Maps → Combinational → Adders/ALU → Flip-Flops → Registers → Counters → FSM → Memory → CPU

Each module builds on the previous one. Every folder contains its own `README.md` with:

- 📖 Concept explanation (English + Persian)
- 🧮 Boolean equations and truth tables
- 🔧 Circuit diagrams and Logisim files
- 💻 Verilog source code
- ✅ Exercises and solutions

---

## 💡 Sample: Full Adder in Verilog

```verilog
// 05_adders/full_adder.v
module full_adder(
    input  a,
    input  b,
    input  cin,
    output sum,
    output cout
);
    wire s1, c1, c2;
    xor (s1, a, b);
    xor (sum, s1, cin);
    and (c1, a, b);
    and (c2, s1, cin);
    or  (cout, c1, c2);
endmodule
```

## 🐍 Sample: Truth Table Generator in Python

```python
# 02_boolean_algebra/truth_table.py
from itertools import product

def truth_table(expr, variables):
    """Generate truth table for a boolean expression."""
    print(" | ".join(variables) + " | Result")
    print("-" * (len(variables) * 4 + 10))
    for values in product([0, 1], repeat=len(variables)):
        env = dict(zip(variables, values))
        result = int(eval(expr, {"__builtins__": {}}, env))
        row = " | ".join(str(v) for v in values)
        print(f"{row} |   {result}")

truth_table("A and (B or not C)", ["A", "B", "C"])
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. 🐛 Report bugs or typos via Issues
2. 💡 Suggest new circuits or topics via Discussions
3. 🔧 Submit improvements via Pull Requests

Please read `CONTRIBUTING.md` before submitting PRs.

---

## 📄 License

This project is licensed under the MIT License — see `LICENSE` for details.

---

## ⭐ Support

If this repository helped you understand logic circuits, please consider giving it a star ⭐ — it helps others find it too!

---

## 📬 Contact

- Author: Hasti Amiri
- GitHub: [@HASTIAMIRI5](https://github.com/HASTIAMIRI5)
- Email: hastiamiri418@gmail.com

---

<p align="center">
  <i>Made with ❤️ for everyone learning digital logic</i>
</p>
