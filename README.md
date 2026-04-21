# Hardware Validation of PV Boost Converter with MPPT and PID Control  
## (Proteus-Based Prototype for Thesis Implementation)

## 📘 Thesis Context
This repository documents the hardware validation stage of the thesis titled:

**"Design and Analysis of a PV Boost Converter with MPPT PID Control: Simulation and Proteus Prototypes"**

---

## 🎯 Objective
To validate the proposed PV boost converter system using Proteus simulation before real hardware implementation.

---

## 🖼️ Circuit & Model Overview

### 🔹 Proteus Simulation Setup
The following diagram shows the overall Proteus simulation framework used for hardware validation, including PV emulation, sensing circuits, boost converter, and Arduino-based control system.

![Proteus Simulation Guide](https://i.ibb.co.com/wZnG8JDP/proteus-simulation-guide.png)

---

### 🔹 System Model Architecture
This figure represents the detailed system model of the PV boost converter with MPPT and PID control, including sensing, power stage, and control loop integration.

![System Model](https://i.ibb.co.com/CK3kRQt3/model.png)

---

## ⚡ PV Source Emulation
A programmable DC source is used to emulate a 150.5 W PV module:

- Voc ≈ 20.5 V  
- Isc ≈ 9 A  

This enables controlled variation of solar input conditions.

---

## 🔌 Signal Conditioning

### Voltage Divider Networks
- 6.8 kΩ / 1 kΩ  
- 13 kΩ / 1 kΩ  

### Current Sensing
- ACS712 Hall-effect sensor  
- Provides isolated real-time current measurement  

---

## ⚙️ Boost Converter Hardware

| Component | Specification |
|----------|--------------|
| Inductor | 6 mH |
| MOSFET | IRL540NS |
| Diode | Schottky |
| Capacitors | 300 µF + 460 µF |

---

## 🧠 Control System

Implemented on Arduino UNO:

- MPPT algorithm for maximum power tracking  
- PID controller for output stability  
- PWM switching at ~5 kHz  

---

## 📊 Key Results

- Stable output voltage ≈ 70 V  
- Fast transient response  
- Minimal oscillations  
- Accurate MPPT tracking  

---

## 📌 Conclusion
The Proteus-based validation confirms that the proposed PV boost converter with MPPT and PID control is:

- Stable  
- Efficient  
- Hardware implementable  
- Suitable for renewable energy applications  
