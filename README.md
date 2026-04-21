# Hardware Validation of PV Boost Converter with MPPT and PID Control  
## (Proteus-Based Prototype for Thesis Implementation)

## 📘 Thesis Context
This repository documents the hardware validation stage of the thesis titled:

**"Design and Analysis of a PV Boost Converter with MPPT PID Control: Simulation and Proteus Prototypes"**

The objective of this stage is to validate the proposed Maximum Power Point Tracking (MPPT) and PID-controlled boost converter architecture using a circuit-level simulation environment (Proteus 8 Professional) before real hardware implementation.

---

## 🎯 Objective
To verify the performance, stability, and feasibility of the proposed PV energy harvesting system by:

- Emulating a photovoltaic (PV) source using a programmable DC supply
- Implementing a boost converter with real component models
- Deploying Arduino-based MPPT and PID control logic
- Observing system behavior under variable input conditions

---

## ⚡ PV Source Emulation

Since Proteus does not include a dedicated PV array model, a **programmable DC source** is used to simulate solar panel characteristics:

- Rated Power: **150.5 W**
- Open Circuit Voltage (Voc): ≈ **20.5 V**
- Short Circuit Current (Isc): ≈ **9 A**

This approach allows controlled variation of input voltage to replicate changing irradiance conditions.

---

## 🔌 Signal Conditioning and Sensing

### Voltage Measurement
Two precision resistor dividers are used for safe ADC interfacing with Arduino UNO:

- 6.8 kΩ / 1 kΩ divider  
- 13 kΩ / 1 kΩ divider  

These networks scale PV voltage into the 0–5 V ADC range.

### Current Measurement
- Sensor: **ACS712 Hall-effect current sensor**
- Function: Provides galvanically isolated real-time current feedback
- Advantage: Noise immunity and safe microcontroller interfacing

---

## ⚙️ Power Converter Design

The boost converter stage is designed to achieve high-efficiency voltage step-up:

| Component | Specification |
|----------|--------------|
| Inductor | 6 mH |
| MOSFET | IRL540NS (logic-level) |
| Diode | Schottky diode (fast recovery) |
| Output Capacitors | 300 µF + 460 µF |

### Design Features
- Supports high duty-cycle operation
- Reduces output ripple
- Improves dynamic response and conversion efficiency

---

## 🧠 Control System Architecture

The control strategy is implemented on **Arduino Uno** and consists of:

### 🔹 MPPT Algorithm
- Continuously samples voltage and current
- Computes instantaneous power (P = V × I)
- Adjusts operating point to maximize power extraction

### 🔹 PID Controller
- Stabilizes output voltage
- Reduces oscillations around MPP
- Enhances transient response

### 🔹 PWM Generation
- Frequency: ~5 kHz
- Output drives MOSFET gate
- Duty cycle dynamically adjusted in real-time

---

## 📊 Simulation Results

The Proteus-based validation demonstrated:

- Stable boosted output voltage ≈ **70 V**
- Fast convergence to Maximum Power Point
- Low steady-state oscillations
- Accurate duty-cycle tracking under variable input
- Robust closed-loop performance under transient conditions

---

## 🧪 Key Outcomes

- Validated MPPT + PID hybrid control strategy
- Confirmed boost converter stability under dynamic input
- Verified sensor integration with Arduino ADC system
- Demonstrated hardware feasibility of simulation model

---

## 🧱 Hardware Implementation Readiness

The Proteus schematic directly maps to physical implementation using:

- Arduino Uno (or equivalent microcontroller)
- ACS712 current sensor
- Resistive voltage divider network
- Standard boost converter components

This ensures a **direct transition from simulation to prototype fabrication** without architectural modification.

---

## 📌 Conclusion

This hardware validation confirms that the proposed PV boost converter system with MPPT and PID control is:

- Technically feasible  
- Stable under dynamic conditions  
- Suitable for real-world renewable energy applications  

It forms a validated foundation for experimental hardware development and further optimization in future work.

---
