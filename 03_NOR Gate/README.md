# 2-Input CMOS NOR Gate Design and Analysis (Cadence Virtuoso)

## 📌 Overview

This project demonstrates the design and simulation of a 2-input CMOS NOR gate using Cadence Virtuoso. The circuit is verified using transient analysis and DC sweep to observe its logical behavior and voltage transfer characteristics (VTC).

---

## 🛠️ Tools Used

* Cadence Virtuoso Schematic Editor
* Spectre Simulator

---

## ⚙️ Circuit Description

The CMOS NOR gate is implemented using complementary MOS transistors:

### PMOS Network (Pull-Up)

* Two PMOS transistors connected in **series**
* Connected to VDD
* Gates driven by inputs A and B

### NMOS Network (Pull-Down)

* Two NMOS transistors connected in **parallel**
* Connected to GND (VSS)
* Gates driven by inputs A and B

### Output

* Taken from the node between pull-up and pull-down networks

---

## 🔄 Transient Analysis

### Input Configuration

* **Input A:** Fast pulse signal
* **Input B:** Slow pulse signal

This ensures all input combinations are tested.

---

## 📊 Observation

The output follows NOR logic:

| A | B | Output |
| - | - | ------ |
| 0 | 0 | 1      |
| 0 | 1 | 0      |
| 1 | 0 | 0      |
| 1 | 1 | 0      |

* Output is HIGH only when both inputs are LOW
* Confirms correct NOR functionality


## 📉 DC Analysis (VTC)

Since NOR has two inputs, VTC is obtained by fixing one input and sweeping the other.

### Method:

* Fix input **B = 0V**
* Sweep input **A from 0V to 1.8V**

### Observation:

* NOR behaves like an inverter when one input is LOW
* Correct switching behavior is observed

---

## 📷 Results

* NOR schematic
* Testbench circuit
* Transient waveform
* VTC curve

---

## 🎯 Conclusion

The CMOS NOR gate was successfully designed and verified using Cadence Virtuoso. Transient analysis confirms correct logical behavior, and DC analysis validates the voltage transfer characteristics. Observed glitches highlight real-world non-ideal switching effects.

