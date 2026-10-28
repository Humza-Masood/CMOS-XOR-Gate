
# Transistor-Level CMOS XOR Gate

Design, hardware implementation, and performance characterization of a transistor-level CMOS XOR gate using complementary NMOS and PMOS transistor networks.

This project focuses on digital circuit design, transistor sizing analysis, functional verification, and switching performance under capacitive loading.

## Technical Overview

| Parameter | Description |
|---|---|
| Logic Function | 2-input XOR (Exclusive OR) |
| Circuit Architecture | Complementary CMOS |
| Hardware | CD4007 MOSFET Arrays |
| Supply Voltage | 5 V |
| Design Methodology | NMOS/PMOS Pull-Up and Pull-Down Networks |
| Verification | Digital I/O, Oscilloscope, Timing Analysis |
| Output Load | 100 nF Capacitor |

## Circuit Design

The XOR gate implements the Boolean expression:

**Y = A XOR B = (NOT A AND B) OR (A AND NOT B)**

The circuit uses complementary CMOS transistor networks:

- **Pull-Down Network (PDN):** NMOS transistors arranged in two parallel branches, each containing two series-connected transistors.
- **Pull-Up Network (PUN):** Complementary PMOS network that drives the output HIGH when the inputs differ.
- **Input Inversion:** Two CMOS inverters generate the complemented input signals required by the transistor networks.

The circuit was constructed using CD4007 MOSFET arrays to implement the required logic functionality.

### Transistor Sizing Analysis

Transistor sizing was analyzed to balance the effective resistance of the pull-up and pull-down networks.

Series-connected transistors increase effective resistance, requiring larger device widths to maintain switching performance comparable to a reference inverter.

The theoretical sizing calculations produced:

| Transistor Type | Calculated W/L Ratio |
|---|---|
| NMOS | 4:1 |
| PMOS | 10:1 |

These ratios represent theoretical design targets. The physical implementation used CD4007 arrays with manufacturer-defined transistor dimensions, preventing exact realization of the calculated sizing ratios.

## Hardware Implementation

The circuit was physically constructed and tested using CD4007 MOSFET arrays.

The hardware implementation involved:

- Constructing complementary NMOS and PMOS transistor networks.
- Implementing CMOS inverters to generate inverted input signals.
- Connecting digital input signals to control the XOR operation.
- Measuring output voltage levels and verifying digital functionality.
- Characterizing switching performance under a 100 nF capacitive load.

## Functional Verification

All four possible input combinations were tested using digital I/O signals.

The measured outputs matched the expected XOR truth table.

| Input A | Input B | Output Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### Static Logic-Level Measurements

Static voltage measurements confirmed near rail-to-rail operation.

| Parameter | Measured Value |
|---|---|
| Logic HIGH | 4.97 V |
| Logic LOW | 0.01 V |

The measured voltage levels demonstrate that the CMOS network successfully produces distinct HIGH and LOW outputs under the tested conditions.

## Switching Performance

Dynamic timing measurements were performed by driving one input with a 0–5 V square wave while holding the other input HIGH.

A 100 nF capacitor was connected to the output to simulate capacitive loading.

### Measured Timing Parameters

| Parameter | Measured Value |
|---|---|
| Rise Time | 457 µs |
| Fall Time | 490 µs |
| Low-to-High Propagation Delay | 176 µs |
| High-to-Low Propagation Delay | 201 µs |
| Average Propagation Delay | 188.5 µs |

The average propagation delay was calculated as the mean of the low-to-high and high-to-low propagation delays:

**Average Propagation Delay = (176 µs + 201 µs) / 2 = 188.5 µs**

These results characterize the dynamic response of the transistor-level XOR gate under the specified capacitive load.

## Engineering Outcomes

This project demonstrated practical experience in:

- **CMOS Digital Logic:** Designing complementary NMOS/PMOS transistor networks to implement XOR functionality.
- **Transistor-Level Design:** Analyzing pull-up/pull-down resistance and transistor sizing requirements.
- **Hardware Implementation:** Constructing and testing a physical CMOS logic circuit.
- **Functional Verification:** Validating all four digital input combinations and measuring static output levels.
- **Timing Characterization:** Measuring rise time, fall time, and propagation delay under capacitive loading.
- **Hardware Debugging:** Using digital I/O and waveform measurements to assess circuit operation.

## Documentation

The complete technical report includes:

- Transistor-level circuit schematic
- CMOS transistor sizing calculations
- Physical hardware implementation
- Functional verification results
- Static voltage measurements
- Propagation delay and switching waveform analysis
