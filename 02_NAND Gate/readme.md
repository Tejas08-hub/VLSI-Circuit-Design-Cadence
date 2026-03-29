\# 2-Input CMOS NAND Gate Design and Analysis (Cadence Virtuoso)



\## 📌 Overview



This project demonstrates the design and simulation of a 2-input CMOS NAND gate using Cadence Virtuoso. The circuit is verified using transient analysis and DC sweep to observe its logical behavior and voltage transfer characteristics (VTC).



---



\## 🛠️ Tools Used



\* Cadence Virtuoso Schematic Editor

\* Spectre Simulator



---



\## ⚙️ Circuit Description



The CMOS NAND gate is implemented using complementary MOS transistors:



\* \*\*PMOS Network (Pull-Up):\*\*



&nbsp; \* Two PMOS transistors connected in \*\*parallel\*\*

&nbsp; \* Connected to VDD

&nbsp; \* Gates driven by inputs A and B



\* \*\*NMOS Network (Pull-Down):\*\*



&nbsp; \* Two NMOS transistors connected in \*\*series\*\*

&nbsp; \* Connected to GND (VSS)

&nbsp; \* Gates driven by inputs A and B



\* \*\*Output (Vout):\*\*



&nbsp; \* Taken from the node between pull-up and pull-down networks



---



\## 🔄 Transient Analysis



\### Input Configuration



Two pulse inputs are applied:



\* \*\*Input A (fast signal):\*\*



&nbsp; \* V1 = 0V, V2 = 1.8V

&nbsp; \* Period = 20 ns



\* \*\*Input B (slow signal):\*\*



&nbsp; \* V1 = 0V, V2 = 1.8V

&nbsp; \* Period = 40 ns



This ensures all possible input combinations are covered.



---



\### 📊 Observation



The output follows NAND logic:



| A | B | Vout |

| - | - | ---- |

| 0 | 0 | 1    |

| 0 | 1 | 1    |

| 1 | 0 | 1    |

| 1 | 1 | 0    |



\* Output remains HIGH for all cases except when both inputs are HIGH

\* Confirms correct NAND functionality



---



\## ⚠️ Glitch Observation (Dynamic Hazard)



During simulation, small glitches are observed at the output.



\### Reason:



\* Inputs A and B switch at different times

\* Unequal propagation delays in PMOS and NMOS networks

\* Temporary intermediate states occur



\### Conclusion:



These glitches are \*\*normal in CMOS combinational circuits\*\* and are known as \*\*dynamic hazards\*\*.



---



\## 📉 DC Analysis (VTC)



Since NAND has two inputs, VTC is obtained by fixing one input and sweeping the other.



\### Method:



\* Fix input \*\*B = 1.8V\*\*

\* Sweep input \*\*A from 0V to 1.8V\*\*



\### Observation:



\* NAND behaves like an inverter when one input is HIGH

\* Proper switching behavior is observed



---



\## 📷 Results



\* NAND schematic

\* Testbench circuit

\* Transient waveform

\* VTC curve



---



\## 🎯 Conclusion



The CMOS NAND gate was successfully designed and verified. Transient analysis confirms correct logical operation, and DC analysis validates its voltage transfer behavior. Observed glitches highlight real-world non-ideal switching effects in CMOS circuits.

