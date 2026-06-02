# CMOS XNOR Gate Design

## Objective

Design and verify a CMOS XNOR gate in Cadence Virtuoso using complementary CMOS logic at the transistor level.

---

## Theory

The XNOR (Exclusive-NOR) gate produces a logic HIGH only when both inputs are equal.

### Truth Table

| A | B | XNOR |
|---|---|------|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### Boolean Expression

```
Y = AB + A'B'
```

---

## Design Methodology

The XNOR gate was implemented using complementary CMOS logic consisting of:

- PMOS Pull-Up Network (PUN)
- NMOS Pull-Down Network (PDN)

---

## CMOS Implementation

### PMOS Pull-Up Network

The PMOS network implements:

```
AB + A'B'
```

Structure:

- PMOS(A) in series with PMOS(B)
- PMOS(A') in series with PMOS(B')
- Both branches connected in parallel

The pull-up network provides a path from VDD to the output when:

```
A = B
```

thus generating logic HIGH.

---

### NMOS Pull-Down Network

The NMOS network implements the complement of XNOR:

```
A'B + AB'
```

Structure:

- NMOS(A') in series with NMOS(B)
- NMOS(A) in series with NMOS(B')
- Both branches connected in parallel

The pull-down network provides a path from the output to ground whenever:

```
A ≠ B
```

thus generating logic LOW.

---

## Why the NMOS Network Implements XOR

A common confusion in CMOS design is why the NMOS network implements:

```
A'B + AB'
```

instead of:

```
AB + A'B'
```

The reason is that:

- PMOS network determines when the output becomes HIGH.
- NMOS network determines when the output becomes LOW.

Since the XNOR output is HIGH for:

```
AB + A'B'
```

the output becomes LOW for:

```
A'B + AB'
```

Therefore, the NMOS pull-down network implements the complement of the XNOR function.

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

---

## Results

The simulated output matched the XNOR truth table.

| A | B | XNOR Output |
|---|---|-------------|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

The output achieved full voltage swing from 0V to 1.8V.

---

## Key Learning Outcomes

- Understanding of complementary CMOS logic.
- CMOS Pull-Up and Pull-Down network design.
- Relationship between XOR and XNOR functions.
- Application of Boolean algebra in transistor-level design.
- Verification of digital circuits using transient simulation in Cadence Virtuoso.

---

## Conclusion

A transistor-level CMOS XNOR gate was successfully designed and verified in Cadence Virtuoso using complementary CMOS logic. The design demonstrated correct XNOR functionality and provided practical experience in CMOS logic synthesis, simulation, and verification.

---

**Tool:** Cadence Virtuoso  
**Technology:** GPDK 90nm  
**Author:** Tejas K