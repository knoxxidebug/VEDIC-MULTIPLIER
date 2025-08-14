Vedic Multiplier (4×4, Verilog)
📌 Overview

This project implements a 4-bit × 4-bit Vedic Multiplier in Verilog, producing an 8-bit output.
It uses the Urdhva Tiryakbhyam Sutra ("Vertically and Crosswise") from Vedic mathematics to perform fast multiplication.
The design is modular, breaking the multiplication into 2×2 blocks and then combining results using ripple-carry adders.

🛠 Features

Multiplies two 4-bit inputs to produce an 8-bit product.

Based on Vedic multiplication for reduced delay compared to traditional array multipliers.

Modular design:

two_bit – Multiplies two 2-bit numbers.

ripple_add – Adds partial products.

vedic – Top-level 4×4 multiplier combining submodules.

Easily scalable to higher bit-widths.
📜 Module Descriptions
1. two_bit

Takes two 2-bit numbers and produces a 4-bit product.

Used as building blocks for larger multipliers.

2. ripple_add

Adds two 4-bit numbers (plus carry) using a ripple-carry approach.

Used to sum partial products in the multiplication process.

3. vedic (Top Level)

Inputs: A[3:0], B[3:0] (two 4-bit numbers)

Output: OUT[7:0] (8-bit product)

Process:

Split A and B into 2-bit halves.

Multiply lower halves and store in OUT[0] and OUT[1].

Multiply cross-pairs and add results using ripple_add.

Multiply upper halves and add to final partial sum.

⚙ Working Principle (Urdhva Tiryakbhyam)

The Vedic multiplication method works vertically and crosswise:

Multiply the least significant bits → write to product’s LSB.

Multiply and sum crosswise terms → middle bits.

Multiply the most significant bits → product’s MSB.

Combine all results using adders.

This method minimizes carry propagation and improves speed.
