# 0_KiCAD-and-PCB-Design
# Simple LED Driver Circuit

A foundational, low-power hardware design featuring a single-cell battery source, a current-limiting resistor, and a Light Emitting Diode (LED). This project serves as a clean baseline for schematic capture, electrical rule checking (ERC), custom footprint assignment, and manufacturing output generation using KiCad.

---

##  Project Overview

The objective of this project is to implement a robust, reliable, and mathematically sound LED indicator loop. LEDs are non-linear components with negligible internal resistance once their forward voltage threshold is crossed. To prevent over-current conditions and immediate component failure, this circuit incorporates a precisely calculated series resistor acting as a dedicated current limiter.

### Key Specifications
* **Supply Voltage ($V_{CC}$):** 3.0V DC (Optimized for standard CR2032 or dual AA/AAA battery configurations)
* **Target Forward Current ($I_f$):** ~10mA to 15mA (Balances ideal brightness with battery longevity)
* **Form Factor:** Minimalist PCB, routing single-sided or dual-layer copper tracks.

---

## 📊 Schematic & Circuit Design

The circuit is designed entirely within the **KiCad Schematic Editor**. The architecture utilizes explicit power distribution nets to decouple the power generation node from the functional loop.

### Component Breakdown
* **BT101 (Battery_Cell):** Direct current (DC) source providing system potential.
* **R101 (R_US):** Current-limiting resistor configured using the US-style schematic symbol.
* **D101 (LED):** Standard semiconductor diode indicator.
* **PWR_FLAG:** KiCad utility power flags appended to the `VCC` and `GND` nets to explicitly declare power-generating pins and successfully satisfy Electrical Rules Check (ERC) compilation.

### The Physics (Ohm's Law Calculation)
To ensure optimal current regulation, the resistor value was derived using the standard load equation:

$$R = \frac{V_{CC} - V_f}{I_f}$$

*Where $V_f$ represents the forward voltage drop characteristic of the selected LED substrate (typically 1.8V to 2.1V for standard red/green indicators).*

---

## 🎨 PCB Layout & Manufacturing Best Practices

The physical implementation of the layout adheres strictly to industry-standard DFM (Design for Manufacturability) guidelines:

---
