# 1-Bit Full Adder Design & Optimisation — Cadence Virtuoso

## Overview

This project presents the **design, simulation, and comparative analysis** of a 1-bit Full Adder implemented at the **transistor level** using Cadence Virtuoso EDA tools.

Five different logic styles were designed and evaluated to understand trade-offs between:

* Power consumption
* Propagation delay
* Transistor count (area)

The objective is to identify the most efficient topology for **low-power, high-speed VLSI applications**.

---

## Full Adder Fundamentals

A 1-bit Full Adder adds three binary inputs:

* A (input bit)
* B (input bit)
* Cin (carry input)

### Boolean Equations

```id="eq1"
Sum  = A ⊕ B ⊕ Cin
Cout = (A · B) + (B · Cin) + (A · Cin)
```

### Truth Table

| A | B | Cin | Sum | Cout |
| - | - | --- | --- | ---- |
| 0 | 0 | 0   | 0   | 0    |
| 0 | 0 | 1   | 1   | 0    |
| 0 | 1 | 0   | 1   | 0    |
| 0 | 1 | 1   | 0   | 1    |
| 1 | 0 | 0   | 1   | 0    |
| 1 | 0 | 1   | 0   | 1    |
| 1 | 1 | 0   | 0   | 1    |
| 1 | 1 | 1   | 1   | 1    |

---

## Objectives

* Design five transistor-level full adder circuits
* Perform transient simulations using Spectre
* Measure propagation delay (Cin → Sum and Cin → Cout)
* Evaluate power consumption
* Compare area using transistor count
* Identify optimal design topology

---

## Tools & Technologies

* Cadence Virtuoso Schematic Editor
* Spectre Simulator
* Analog Design Environment (ADE)
* CMOS Process Design Kit (PDK)
* Virtuoso Waveform Viewer

---

## Design Methodology

### Schematic Design

Each full adder was implemented using CMOS transistors in Virtuoso.
Different logic styles were used to optimize performance.

### Simulation Setup

* Supply Voltage (VDD): 1.8V / 3.3V
* Analysis Type: Transient
* Inputs: Piecewise linear signals (A, B, Cin)
* Delay Measurement: 50% voltage crossing method
* Power Measurement: From VDD supply

### Metrics Evaluated

* Propagation delay
* Average power consumption
* Transistor count

---

## Implemented Topologies

### 1. Static CMOS Full Adder

* Uses complementary PMOS and NMOS networks
* High reliability and full voltage swing
* Disadvantages:

  * High transistor count (~24)
  * High power consumption
  * Larger delay

---

### 2. Hybrid CMOS Full Adder

* Combines CMOS logic with pass/transmission gates
* Advantages:

  * Reduced transistor count
  * Improved speed
  * Lower power than static CMOS

---

### 3. Pass Transistor Logic (PTL)

* Uses transistors as switches to pass signals
* Advantages:

  * Reduced area
* Limitations:

  * Threshold voltage drop
  * Requires restoration circuits

---

### 4. GDI-Based Full Adder

* Uses Gate Diffusion Input (GDI) technique
* Very efficient implementation using fewer transistors
* Advantages:

  * Low power
  * High speed
  * Reduced area

---

### 5. Hybrid GDI Full Adder

* Combines GDI with CMOS inverters
* Optimizes both performance and signal integrity
* Advantages:

  * Lowest transistor count (~14)
  * Lowest power consumption
  * Fastest operation

---

## Performance Comparison

| Circuit | Topology    | Transistors | Power    | Delay (Sum) | Delay (Cout) |
| ------- | ----------- | ----------- | -------- | ----------- | ------------ |
| 1       | Static CMOS | ~24         | High     | ~1.135 ns   | ~147.5 ns    |
| 2       | Hybrid CMOS | ~20         | Low      | ~66.16 ps   | ~115.6 ps    |
| 3       | PTL         | ~18         | Medium   | ~2.873 ns   | ~2.918 ns    |
| 4       | GDI         | ~16         | Very Low | ~86.85 ps   | ~110.7 ps    |
| 5       | Hybrid GDI  | ~14         | Lowest   | ~65.19 ps   | ~104.4 ps    |

---

## Key Observations

* Static CMOS is reliable but inefficient in power and speed
* Hybrid CMOS improves performance significantly
* PTL reduces area but suffers in delay
* GDI drastically reduces power and transistor count
* Hybrid GDI provides the best overall optimization

---

## Final Result

The **Hybrid GDI Full Adder (Circuit 5)** is the optimal design:

* Fastest propagation delay (~65 ps)
* Lowest power consumption
* Minimum transistor count

---

## Applications

* Arithmetic Logic Units (ALUs)
* Microprocessors
* Digital Signal Processing (DSP)
* Low-power embedded systems

---

## Future Work

* Layout design and parasitic extraction
* Multi-bit adder implementation
* Carry Lookahead Adder design
* Fabrication-level analysis

---

## Team

* Manasa V G (24BEC1419)
* Shruthi Narayanan (24BEC1458)
* Swetha S (24BEC1042)
* Janieshree P (24BEC1088)

---

## Institution

VIT Chennai
Department of Electronics and Communication Engineering
VLSI Design Laboratory (2025–2026)

Under the guidance of
Dr. Manikandan P

---

## References

* CMOS VLSI Design — Weste & Harris
* Digital Integrated Circuits — Rabaey
* IEEE papers on GDI and Full Adder Design
* Cadence Virtuoso Documentation
