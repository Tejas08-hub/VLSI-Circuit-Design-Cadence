# Transmission Gate Based 2:1 Multiplexer Design in Cadence Virtuoso

## Objective

To design, implement, and verify a **2:1 Multiplexer (MUX)** using **Transmission Gate (TG) logic** in Cadence Virtuoso and validate its functionality through transient simulation.

---

## Introduction

A Multiplexer (MUX) is a combinational logic circuit that selects one of several input signals and forwards the selected input to a single output line.

A **2:1 Multiplexer** has:

* Two data inputs: **A** and **B**
* One select input: **S**
* One output: **Y**

The output depends on the value of the select signal.

---

## Boolean Expression

The output equation of a 2:1 Multiplexer is:

Y = S̅A + SB

Where:

* S = Select signal
* A = Input 0
* B = Input 1
* Y = Output

---

## Truth Table

| S | A | B | Y |
| - | - | - | - |
| 0 | 0 | X | 0 |
| 0 | 1 | X | 1 |
| 1 | X | 0 | 0 |
| 1 | X | 1 | 1 |

(X = Don't Care)

---

## Why Transmission Gates?

A transmission gate consists of:

* One NMOS transistor
* One PMOS transistor

connected in parallel with complementary control signals.

Advantages:

* Passes a strong logic '1'
* Passes a strong logic '0'
* Eliminates threshold voltage degradation
* Requires fewer transistors compared to conventional CMOS implementations
* Widely used in multiplexers, latches, and flip-flops

---

## Design Methodology

### Step 1: Generate Complementary Select Signal

An inverter is used to generate:

S̅ = NOT(S)

The select signal and its complement are required to control the transmission gates.

---

### Step 2: Transmission Gate for Input A

The first transmission gate is connected to input **A**.

Control signals:

* NMOS Gate = S̅
* PMOS Gate = S

Operation:

* ON when S = 0
* OFF when S = 1

Therefore, input **A** is selected whenever the select signal is LOW.

---

### Step 3: Transmission Gate for Input B

The second transmission gate is connected to input **B**.

Control signals:

* NMOS Gate = S
* PMOS Gate = S̅

Operation:

* ON when S = 1
* OFF when S = 0

Therefore, input **B** is selected whenever the select signal is HIGH.

---

### Step 4: Output Formation

The outputs of both transmission gates are connected together to form the final output node.

Result:

* When S = 0 → Y = A
* When S = 1 → Y = B

This realizes the 2:1 multiplexer function:

Y = S̅A + SB

---

## Circuit Components

The design uses:

* 2 PMOS transistors
* 2 NMOS transistors
* 1 CMOS inverter

Total transistor count:

* Transmission Gates = 4 transistors
* Inverter = 2 transistors

Total = 6 transistors

---

## Simulation Setup

### Supply Voltage

VDD = 1.8 V

VSS = 0 V

### Input Signals

#### Input A

* Pulse Voltage: 0 V to 1.8 V
* Period: 40 ns

#### Input B

* Pulse Voltage: 0 V to 1.8 V
* Period: 80 ns

#### Select Signal S

* Pulse Voltage: 0 V to 1.8 V
* Period: 160 ns

These different periods ensure all input combinations are exercised during simulation.

---

## Verification

The following signals were observed:

* A
* B
* S
* Vout

Observed behavior:

### When S = 0

The output follows input A.

Y = A

### When S = 1

The output follows input B.

Y = B

The transient response confirms the correct functionality of the transmission-gate-based multiplexer.

---

## Results

* Successful implementation of a 2:1 MUX using transmission gates
* Correct output obtained for all input combinations
* Full voltage swing observed at the output
* No threshold voltage loss due to complementary NMOS-PMOS conduction
* Functional verification completed through transient simulation

---

## Applications

* Data selection circuits
* Processor datapaths
* Memory addressing circuits
* Communication systems
* Latches and flip-flops
* VLSI datapath design

---

## Conclusion

A 2:1 Multiplexer was successfully designed using transmission gate logic in Cadence Virtuoso. The circuit was verified through transient analysis and demonstrated correct input selection based on the select signal. The design achieves full voltage swing, reduced transistor count, and efficient switching characteristics, making it suitable for high-performance VLSI applications.
