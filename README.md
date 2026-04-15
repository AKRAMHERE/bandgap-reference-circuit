# CMOS Bandgap Reference Circuit (PTAT-Based Implementation) (Generated with AI help)

## Overview
This project presents the design and simulation of a CMOS-based voltage reference circuit using LTspice. The circuit implements a PTAT (Proportional-To-Absolute-Temperature) voltage generation mechanism using current mirrors and diode-connected devices.

The design attempts to approximate a bandgap reference but currently demonstrates dominant PTAT behavior due to the absence of CTAT compensation.

---

## Circuit Description

The circuit consists of:

- NMOS and PMOS current mirrors for biasing
- Diode-connected devices to generate temperature-dependent voltages
- Resistor network for current scaling and voltage generation

Key principle used:

\[
\Delta V_{BE} = V_T \ln(n)
\]

where:

- \( V_T = \frac{kT}{q} \)
- \( n \) is the current ratio

The output voltage is approximately:

\[
V_{out} \approx \frac{R3}{R1} \cdot \Delta V_{BE}
\]

---

## Simulation Setup

- Tool: LTspice
- DC Sweep: 0V to 5V
- Temperature Sweep: 0°C, 25°C, 50°C, 75°C, 100°C

---

## Results

- Output voltage increases with temperature
- Strong PTAT behavior observed (~mV/°C slope)
- Output range: ~0.75 V to ~1.05 V (depending on temperature)

This confirms:

- Proper biasing and current mirror operation
- Absence of temperature compensation

---

## Key Observations

- The circuit successfully generates PTAT voltage
- Temperature coefficient is positive and significant
- No CTAT component is present, so output is not temperature-independent

---

## Limitations

- Not a true bandgap reference
- Missing CTAT term (\( V_{BE} \))
- Output voltage varies significantly with temperature

---

## Future Improvements

- Introduce CTAT component using diode-connected BJT
- Implement summation:
  \[
  V_{ref} = V_{BE} + k \cdot \Delta V_{BE}
  \]
- Optimize resistor ratio for temperature cancellation
- Improve matching and layout-aware design

---

## Files

- `BANDGAP_REFERENCE_CIRCUIT.asc` → LTspice schematic
- `Screenshot_annotated.png` → Circuit diagram

---

## Author

Syed Akram Ameer Abbas
