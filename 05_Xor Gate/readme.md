CMOS XOR Gate Design Using XNOR + Inverter
Objective

To design and verify a CMOS XOR gate in Cadence Virtuoso using a transistor-level XNOR gate followed by an inverter.

Theory

The XOR (Exclusive-OR) gate produces a logic HIGH only when the inputs are different.

Truth Table:

A	B	XOR
0	0	0
0	1	1
1	0	1
1	1	0

Boolean Expression:

Y=A
′
B+AB
′

Design Methodology

Instead of directly implementing the XOR function, the design was realized in two stages:

Stage 1: XNOR Gate

The XNOR function is:

Y
XNOR
	​

=AB+A
′
B
′

Truth Table:

A	B	XNOR
0	0	1
0	1	0
1	0	0
1	1	1

The XNOR network was implemented using complementary CMOS logic.

Pull-Up Network (PMOS)

The PMOS network implements:

AB+A
′
B
′

Structure:

Series PMOS pair controlled by A and B
Series PMOS pair controlled by A' and B'
Both branches connected in parallel
Pull-Down Network (NMOS)

The NMOS network implements the complement:

A
′
B+AB
′

Structure:

Series NMOS pair controlled by A' and B
Series NMOS pair controlled by A and B'
Both branches connected in parallel
Stage 2: Inverter

The output of the XNOR gate is passed through a CMOS inverter.

Output equation:

Y=(AB+A
′
B
′
)
′

Applying De Morgan's theorem:

Y=A
′
B+AB
′

which is the XOR function.

Why Not Directly Use A'B + AB'?

A common mistake is to directly construct only the expression:

A
′
B+AB
′

using NMOS transistors and assume that the circuit behaves as an XOR gate.

This is incorrect for static CMOS design.

Reason

In static CMOS:

PMOS Pull-Up Network generates logic HIGH.
NMOS Pull-Down Network generates logic LOW.

The NMOS network must implement the conditions under which the output becomes 0.

For XOR:

Y=A
′
B+AB
′

The output becomes LOW when:

Y
′
=AB+A
′
B
′

Therefore:

PMOS network must realize XOR.
NMOS network must realize XNOR.

If only A'B + AB' is implemented in the NMOS network without constructing the complementary PMOS network, the output node can become floating for some input combinations, resulting in:

Incorrect logic levels
Intermediate voltages
Poor noise margins
Static CMOS violation
Design Parameters

Technology: GPDK 90 nm

Supply Voltage:

VDD = 1.8 V
VSS = 0 V

Initial Device Dimensions:

Device	Width	Length
NMOS	120 nm	180 nm
PMOS	240 nm	180 nm
Simulation Setup

Analysis Type:

Transient Analysis

Input A:

Pulse Source
Period = 40 ns

Input B:

Pulse Source
Period = 80 ns

Observed Signals:

A
B
XNOR output
XOR output
Verification

The simulated waveform verified the following XOR truth table:

A	B	Output
0	0	0
0	1	1
1	0	1
1	1	0

The output exhibited full voltage swing between 0 V and 1.8 V after correcting the supply configuration.

Key Learning Outcomes
Understanding of complementary CMOS design.
Difference between XOR and XNOR implementations.
Relationship between Pull-Up and Pull-Down networks.
Application of De Morgan's theorem in CMOS logic synthesis.
Importance of proper power supply connections.
Verification of transistor-level digital circuits using transient simulation in Cadence Virtuoso.