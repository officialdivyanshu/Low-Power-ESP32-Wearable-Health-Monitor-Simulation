# ESP32 Wearable Heart Rate & SpO₂ Monitor (Wokwi Simulation)

This repository contains the **simulation-level implementation** of a **low-power wearable health monitoring system** using **ESP32** and **I²C peripherals**, validated using the **Wokwi online simulator**.

The project is part of an academic **Low Power VLSI / Embedded Systems wearable project**, focusing on **design correctness, pin mapping, and firmware logic verification** prior to real hardware implementation.

---

## 📌 Project Overview

Wearable health devices require:
- Low power consumption
- Reliable physiological sensing
- Compact and efficient embedded design

This project demonstrates the **functional design and simulation** of a wearable system capable of:
- Heart rate and SpO₂ sensing (via MAX30102 – hardware stage)
- Real-time display output (I²C LCD/OLED)
- Shared I²C bus architecture
- ESP32-based control and processing

⚠️ **Note:** Physiological signal accuracy, battery behavior, and power consumption are validated only during hardware implementation, not in simulation.

---

## 🧠 System Architecture

**Main Controller**
- ESP32 (ESP32-WROOM-32 class)

**Peripherals**
- I²C Display (LCD/OLED)
- MAX30102 Pulse Oximeter & Heart Rate Sensor (logic-level integration)

**Communication Protocol**
- I²C (shared bus)

---

## 🔌 Pin Configuration (Finalized)

| Peripheral | Signal | ESP32 GPIO |
|----------|--------|------------|
| Display | SDA | GPIO 21 |
| Display | SCL | GPIO 22 |
| Display | VCC | 3.3V |
| Display | GND | GND |
| MAX30102 | SDA | GPIO 21 |
| MAX30102 | SCL | GPIO 22 |
| MAX30102 | INT | GPIO 19 |
| MAX30102 | VIN | 3.3V |
| MAX30102 | GND | GND |

✔️ Shared I²C bus design reduces pin usage and power overhead.

---

## 🧪 Simulation Scope (Wokwi)

### ✅ What is validated
- ESP32 firmware logic
- I²C communication
- Display interfacing
- Pin mapping correctness
- Boot and runtime behavior
- Interrupt pin logic (INT)

### ❌ What is NOT simulated
- Real heart rate / SpO₂ waveforms
- Skin-contact noise and motion artifacts
- Battery discharge characteristics
- Charging behavior (TP4056)
- Ultra-low power current consumption

---

## 🛠️ Tools & Technologies

- **Controller:** ESP32
- **Simulator:** Wokwi (https://wokwi.com)
- **Language:** Arduino (C/C++)
- **Protocols:** I²C
- **IDE:** Arduino-compatible environment

---

## 📁 Repository Structure


---

## ▶️ How to Run the Simulation

1. Open **https://wokwi.com**
2. Create a new **ESP32** project
3. Replace:
   - `sketch.ino`
   - `diagram.json`
4. Install required libraries (via Wokwi Library Manager)
5. Click **Start Simulation**
6. Observe Serial Monitor and display output

---

## 🔋 Low Power Design Considerations

Although power consumption cannot be simulated, the design incorporates:
- I²C bus sharing
- Interrupt-based sensor handling
- Minimal GPIO usage
- Compatibility with ESP32 deep-sleep modes

These optimizations are evaluated during the **hardware implementation phase**.

---

## 🚀 Hardware Implementation (Future Work)

Planned hardware extensions include:
- 3.7V Li-ion battery
- TP4056 charging module
- Deep sleep power optimization
- Wearable enclosure integration
- Real-time heart rate & SpO₂ validation

---

## 📄 Academic Note

This repository represents the **simulation and design validation phase** of the project.  
Hardware testing and power analysis are conducted separately due to simulator limitations.

---

## 👤 Author

**Divyanshu Shekhar**  
Electronics & Communication Engineering  
Low Power VLSI / Embedded Systems Project

---

## 📜 License
This project is intended for **academic and educational use**.
