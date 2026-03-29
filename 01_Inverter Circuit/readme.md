# CMOS Inverter Design and Analysis (Cadence Virtuoso)

## 📌 Overview

This project demonstrates the design and simulation of a CMOS inverter using Cadence Virtuoso. The inverter is analyzed using transient and DC simulations to verify its switching behavior and voltage transfer characteristics.

---

## 🛠️ Tools Used

* Cadence Virtuoso Schematic Editor
* Spectre Simulator

---

## ⚙️ Circuit Description

The CMOS inverter is implemented using:

* PMOS transistor connected to VDD
* NMOS transistor connected to GND
* Input applied to both transistor gates
* Output taken from the common drain node

---

## 🔄 Transient Analysis

A pulse input is applied to the inverter:

* V1 = 0V
* V2 = 1.8V
* Period = 40 ns

### 📊 Observation

* Output is the logical inversion of input
* When input is LOW → output is HIGH
* When input is HIGH → output is LOW

This verifies correct inverter operation.

---

## 📉 DC Analysis (Planned)

DC sweep analysis is intended to obtain the Voltage Transfer Characteristic (VTC) curve of the inverter.

---

## 📷 Results

* Schematic of CMOS inverter
* Testbench setup
* Transient response waveform

---

## 🎯 Conclusion

The CMOS inverter was successfully designed and simulated. The transient response confirms correct switching behavior. Further analysis such as DC sweep will help evaluate noise margins and switching threshold.
