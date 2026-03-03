# 🔷 6T SRAM with Dynamic Sense Amplifier (180nm CMOS)

![LTspice](https://img.shields.io/badge/Tool-LTspice-blue)
![Technology](https://img.shields.io/badge/Technology-180nm-orange)
![Supply](https://img.shields.io/badge/VDD-1.8V-green)
![Type](https://img.shields.io/badge/Design-Analog%20CMOS-red)
![Status](https://img.shields.io/badge/Simulation-Verified-brightgreen)

---

## 📌 Project Overview

This project presents the design and simulation of a **6-Transistor (6T) CMOS SRAM cell integrated with a dynamic latch-type sense amplifier** using **180nm CMOS technology** in LTspice.

The design demonstrates:

- Differential bitline read operation
- Dynamic precharge and equalization
- Regenerative latch-based sensing
- Stability and noise margin verification
- Multi-cycle transient validation

Supply Voltage: **1.8 V**

---

## 🧩 Architecture

The complete read path consists of:

### 🔹 6T SRAM Cell
- Two cross-coupled CMOS inverters
- Two access NMOS transistors
- Differential bitlines (BL, BLB)

### 🔹 Precharge Circuit
- Dual PMOS precharge transistors
- Equalization transistor
- Controlled by `Pre_Charge` signal

### 🔹 Dynamic Sense Amplifier
- Cross-coupled PMOS regeneration pair
- Cross-coupled NMOS regeneration pair
- Tail NMOS (SAEN controlled)
- Input gating transistors

---

## ⚙️ Technology Parameters

| Parameter | Value |
|------------|--------|
| Technology Node | 180 nm |
| VDD | 1.8 V |
| Channel Length | 0.18 µm |
| Bitline Capacitance | 100–150 fF |
| MOS Model | Level-1 (Shichman–Hodges) |
| Simulator | LTspice 26 |

---

## 📐 Transistor Sizing

### SRAM Cell

| Device | W (µm) | L (µm) |
|--------|--------|--------|
| Pull-Up PMOS | 0.6 – 2 | 0.18 |
| Pull-Down NMOS | 1 | 0.18 |
| Access NMOS | 0.7 – 1.2 | 0.18 |

### Sense Amplifier

| Device | W (µm) | L (µm) |
|--------|--------|--------|
| Regeneration PMOS | 2 | 0.18 |
| Regeneration NMOS | 3 | 0.18 |
| Tail NMOS | 3 | 0.18 |
| Precharge PMOS | 2–3 | 0.18 |

---

## 🔢 Design Ratios

### Cell Ratio (CR)

\[
CR = \frac{W_{pull-down}}{W_{access}}
\]

Example:
CR ≈ 0.83

---

### Pull-Up Ratio (PR)

\[
PR = \frac{W_{access}}{W_{pull-up}}
\]

Example:
PR ≈ 0.6

---

## ⏱ Operating Phases

### 1️⃣ Precharge Phase
- BL and BLB charged to VDD
- Equalization ON
- Sense amplifier disabled

### 2️⃣ Read Development
- WL asserted
- One bitline discharges slightly
- Small differential voltage develops

### 3️⃣ Sense Amplification
- SAEN asserted
- Tail NMOS activates
- Positive feedback regenerates full rail output

---

## 📊 Simulation Results

| Metric | Approx. Value |
|--------|---------------|
| Hold SNM | ~220–250 mV |
| Read SNM | ~160–190 mV |
| Write Margin | ~300–350 mV |
| Standby Leakage | 20–40 nA |
| Standby Power | ~60 nW |
| Regeneration Delay | Few ns |

---

## 🔍 Observed Behavior

✔ Proper precharge to 1.8 V  
✔ Differential bitline development before sensing  
✔ Strong regenerative latch amplification  
✔ Rail-to-rail output generation  
✔ Stable multi-cycle operation  

Small negative kickback observed during regeneration is expected in dynamic latch simulations.

---

## 🛠 Simulations Performed

- Transient read analysis
- Precharge timing validation
- Sense enable timing sweep
- Bitline loading analysis
- DC sweep for butterfly curve
- Leakage current measurement

---

## 📁 Repository Structure
