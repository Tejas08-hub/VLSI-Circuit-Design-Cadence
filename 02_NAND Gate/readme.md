# 2-Input CMOS NAND Gate Design and Analysis (Cadence Virtuoso)

## 📌 Overview

This project demonstrates the design and simulation of a 2-input CMOS NAND gate using Cadence Virtuoso. The circuit is verified using transient analysis and DC sweep to observe its logical behavior and voltage transfer characteristics (VTC).

---

## 🛠️ Tools Used

* Cadence Virtuoso Schematic Editor
* Spectre Simulator

---

## ⚙️ Circuit Description

The CMOS NAND gate is implemented using complementary MOS transistors:

### PMOS Network (Pull-Up)

* Two PMOS transistors connected in parallel
* Connected to VDD
* Gates driven by inputs A and B

### NMOS Network (Pull-Down)

* Two NMOS transistors connected in series
* Connected to GND (VSS)
* Gates driven by inputs A and B

### Output

* Taken from the node between pull-up and pull-down networks

---

## 🔄 Transient Analysis

### Input Configuration

* Input A: Fast pulse signal
* Input B: Slow pulse signal

This setup ensures all input combinations are tested.

---

## 📊 Observation

The output follows NAND logic:

| A | B | Output |
| - | - | ------ |
| 0 | 0 | 1      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 0      |

* Output remains HIGH for all cases except when both inputs are HIGH
* Confirms correct NAND functionality

---

## ⚠️ Glitch Observation

Small glitches are observed in output due to:

* Unequal propagation delays
* Asynchronous switching of inputs

These are normal in CMOS circuits.

---

## 📉 DC Analysis (VTC)

* One input is fixed
* The other is swept from 0V to 1.8V

This shows inverter-like behavior of NAND under specific conditions.

---

## 🎯 Conclusion

The CMOS NAND gate was successfully designed and verified using Cadence Virtuoso. Both transient and DC analyses confirm correct operation.
