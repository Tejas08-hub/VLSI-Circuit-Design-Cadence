# CMOS D Latch Design and Analysis (Cadence Virtuoso)

## 📌 Overview

This project presents the design and simulation of a CMOS level-sensitive D latch using Cadence Virtuoso. The latch is implemented using transmission gates and inverters, and its functionality is verified through transient analysis.

---

## 🛠️ Tools Used

* Cadence Virtuoso Schematic Editor
* Spectre Simulator

---

## ⚙️ Circuit Description

The D latch is implemented using:

* Two transmission gates (TG1 and TG2)
* Two CMOS inverters
* One inverter to generate the complementary clock (CLK̅)

### 🔹 Transmission Gate Logic

* **TG1 (Input Path):**

  * Controlled by CLK
  * Passes input D when CLK = 1

* **TG2 (Feedback Path):**

  * Controlled by CLK̅
  * Enables feedback when CLK = 0

---

### 🔹 Working Principle

| CLK | Operation                            |
| --- | ------------------------------------ |
| 1   | Transparent mode (Q follows D)       |
| 0   | Hold mode (Q retains previous value) |

* When CLK is HIGH, input D propagates to output Q
* When CLK is LOW, feedback loop stores the previous state

---

## 🔄 Transient Analysis

### Input Configuration

* **Supply Voltage (VDD):** 1.8V

* **Clock (CLK):**

  * V1 = 0V, V2 = 1.8V
  * Period = 40 ns
  * Pulse width = 20 ns

* **Data Input (D):**

  * V1 = 0V, V2 = 1.8V
  * Period = 20 ns
  * Pulse width = 10 ns

---

## 📊 Simulation Results

* Output **Q follows input D** when CLK is HIGH
* Output **Q holds its value** when CLK is LOW
* Complementary output **Q̅ is always inverse of Q**

---

### Conclusion:

These glitches are expected in level-sensitive circuits due to:

* Non-ideal switching delays
* Asynchronous input transitions

---

## 📉 Key Concepts Demonstrated

* Level-sensitive storage behavior
* Transmission gate operation
* Feedback-based memory
* Clock-controlled data flow

---

## 🎯 Conclusion

The CMOS D latch was successfully designed and verified. Simulation results confirm correct level-sensitive behavior, where the output follows the input during the active clock phase and holds the value otherwise.

