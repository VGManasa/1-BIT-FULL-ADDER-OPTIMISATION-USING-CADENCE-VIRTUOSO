# 1-Bit Full Adder Design & Optimisation — Cadence Virtuoso

## Overview
Design, simulation, and performance comparison of five transistor-level 
1-bit full adder topologies using Cadence Virtuoso EDA, optimised for 
power, delay, and area in CMOS technology.

## Topologies Compared
| Circuit | Topology | Transistor Count |
|---|---|---|
| Circuit 1 | Static CMOS | ~24 |
| Circuit 2 | Hybrid CMOS | ~20 |
| Circuit 3 | Pass Transistor Logic (PTL) | ~18 |
| Circuit 4 | GDI-Based | ~16 |
| Circuit 5 | Hybrid GDI | ~14 |

## Tools Used
- Cadence Virtuoso Schematic Editor
- Spectre Simulator (Transient Analysis)
- Analog Design Environment (ADE)
- Virtuoso Waveform Viewer

## Performance Summary
| Circuit | Power | Delay (Sum) | Delay (Cout) |
|---|---|---|---|
| Static CMOS | High | ~1.135 ns | ~147.5 ns |
| Hybrid CMOS | Low | ~66.16 ps | ~115.6 ps |
| Pass Transistor | Medium | ~2.873 ns | ~2.918 ns |
| GDI-Based | Very Low | ~86.85 ps | ~110.7 ps |
| Hybrid GDI | Lowest | ~65.19 ps | ~104.4 ps |

## Key Finding
Hybrid GDI (Circuit 5) achieves the best overall performance —
lowest propagation delay (65.19 ps), lowest power consumption,
and smallest transistor count. Recommended for low-power,
high-speed VLSI applications.

## Tech Stack
Cadence Virtuoso · Spectre Simulator · CMOS PDK · Transient Analysis

## Team
- Manasa V G (24BEC1419)
- Shruthi Narayanan (24BEC1458)
- Swetha S (24BEC1042)
- Janieshree P (24BEC1088)

## Institution
VIT Chennai — VLSI Design Laboratory, Dept. of ECE (2024–2025)
Under guidance of Dr. Manikandan P
