# CMOS XOR Gate Design Using XNOR + Inverter

## Objective

Design and verify a CMOS XOR gate in Cadence Virtuoso using a transistor-level XNOR gate followed by an inverter.

---

## Theory

The XOR (Exclusive-OR) gate produces a logic HIGH only when the inputs are different.

### Truth Table

| A | B | XOR |
|---|---|-----|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### Boolean Expression

```
Y = A'B + AB'
```

---

## Design Methodology

Instead of directly implementing the XOR function, the design was realized in two stages:

### Stage 1: XNOR Gate

The XNOR function is:

```
Y = AB + A'B'
```

### XNOR Truth Table

| A | B | XNOR |
|---|---|------|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

The XNOR network was implemented using complementary CMOS logic.

#### PMOS Pull-Up Network

Implements:

```
AB + A'B'
```

Structure:

- PMOS(A) in series with PMOS(B)
- PMOS(A') in series with PMOS(B')
- Both branches connected in parallel

#### NMOS Pull-Down Network

Implements:

```
A'B + AB'
```

Structure:

- NMOS(A') in series with NMOS(B)
- NMOS(A) in series with NMOS(B')
- Both branches connected in parallel

---

### Stage 2: Inverter

The XNOR output is connected to a CMOS inverter.

```
XOR = (XNOR)'
```

Using De Morgan's theorem:

```
Y = (AB + A'B')'
  = A'B + AB'
```

Thus, the final output becomes XOR.

---

## Why Not Directly Implement A'B + AB'?

A common mistake is to implement only:

```
A'B + AB'
```

and assume that the circuit behaves as a complete CMOS XOR gate.

In static CMOS design:

- PMOS network generates logic HIGH.
- NMOS network generates logic LOW.
- Both networks must be complementary.

If only the expression above is implemented:

- Output node may float.
- Intermediate voltages may appear.
- Noise margin decreases.
- Full rail-to-rail output may not be achieved.

Therefore, complementary PMOS and NMOS networks are required.

---

## Design Parameters

| Parameter | Value |
|------------|--------|
| Technology | GPDK 90nm |
| VDD | 1.8V |
| VSS | 0V |
| NMOS Width | 120nm |
| NMOS Length | 180nm |
| PMOS Width | 240nm |
| PMOS Length | 180nm |

---

## Simulation Setup

### Analysis

```
Transient Analysis
```

### Inputs

- Input A : Pulse Source
- Input B : Pulse Source

### Observed Signals

- A
- B
- XNOR Output
- XOR Output

---

## Results

The simulated output matched the XOR truth table.

| A | B | XOR Output |
|---|---|------------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

The output achieved full voltage swing from 0V to 1.8V.

---

## Conclusion

A transistor-level CMOS XOR gate was successfully designed and verified in Cadence Virtuoso using an XNOR gate followed by an inverter. The design demonstrates complementary CMOS logic principles, Boolean algebra implementation, and transient verification techniques used in VLSI design.
