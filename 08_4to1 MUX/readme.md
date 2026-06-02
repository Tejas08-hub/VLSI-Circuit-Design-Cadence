# CMOS 4:1 Multiplexer Design Using Transmission Gates

## Objective

To design and verify a 4:1 Multiplexer (MUX) in Cadence Virtuoso using Transmission Gate (TG) logic and validate its functionality through transient analysis.

## Theory

A Multiplexer (MUX) is a combinational circuit that selects one of several input signals and forwards the selected input to a single output line.

A 4:1 MUX has:

Inputs:

* A
* B
* C
* D

Select Lines:

* S1
* S0

Output:

* Y

The selected input depends on the values of S1 and S0.

## Truth Table

| S1 | S0 | Output |
| -- | -- | ------ |
| 0  | 0  | A      |
| 0  | 1  | B      |
| 1  | 0  | C      |
| 1  | 1  | D      |

## Boolean Expression

Y = S1'·S0'·A + S1'·S0·B + S1·S0'·C + S1·S0·D

## Design Methodology

The 4:1 MUX was implemented using Transmission Gates in a two-stage structure.

### Stage 1

Two 2:1 MUX blocks were created:

MUX-1 selects between A and B using S0.

Y1 = S0'·A + S0·B

MUX-2 selects between C and D using S0.

Y2 = S0'·C + S0·D

### Stage 2

A third 2:1 MUX selects between Y1 and Y2 using S1.

Y = S1'·Y1 + S1·Y2

Substituting Y1 and Y2 gives the complete 4:1 MUX equation.

## Why Transmission Gates?

A Transmission Gate consists of one NMOS and one PMOS transistor connected in parallel.

Advantages:

* Full voltage swing at the output
* No threshold voltage loss
* Faster switching
* Reduced transistor count
* Efficient CMOS implementation

## Circuit Components

* Transmission Gates for data selection
* Inverters for generating S0', S1'
* VDD = 1.8 V
* VSS = 0 V

## Simulation Setup

Inputs A, B, C and D were applied as pulse sources with different frequencies.

Select lines S0 and S1 were applied as pulse signals to cycle through all possible selection combinations.

Transient analysis was performed to verify operation.

## Expected Operation

When S1S0 = 00, output follows A.

When S1S0 = 01, output follows B.

When S1S0 = 10, output follows C.

When S1S0 = 11, output follows D.

## Results

Transient simulation confirmed correct operation of the 4:1 Multiplexer.

The output successfully followed the selected input for all combinations of S1 and S0.

## Conclusion

A CMOS 4:1 Multiplexer using Transmission Gate logic was successfully designed and simulated in Cadence Virtuoso.

The circuit correctly selected one of four input signals based on the select inputs. Simulation results matched the expected truth table, demonstrating proper functionality of the design.

## Files Included

* Schematic
* Testbench
* Simulation Waveforms
* README
