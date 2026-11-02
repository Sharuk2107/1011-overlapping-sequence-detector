# 1011 Overlapping Sequence Detector with Detection Counter

## Overview
A Proteus-based digital logic implementation that detects occurrences of the binary sequence `1011` in a serial input stream, including overlapping occurrences, and displays the detection count.

## Design
- Four-state finite-state machine representing the progress of matching `1011`.
- FSM state storage implemented using 7474 D flip-flops.
- Combinational next-state and output logic implemented with logic gates.
- A 74LS163 4-bit counter tracks successful detections.
- A seven-segment display presents the count.
- A DPATTERN source supplies a repeatable serial input sequence for simulation.

## Design workflow
1. Drew the state-transition diagram for the four FSM states.
2. Derived the state and output Boolean expressions using a state table and Karnaugh maps.
3. Implemented the FSM and counter/display interface in Proteus 8 Professional.
4. Used logic probes to inspect the FSM output and counter outputs.
5. Tested the circuit with the input sequence documented below.

## Verification
The documented test input was:

`1 0 1 1 0 1 1 0 0 1 0 1 1 0`

The FSM output indicated three detections, and the corrected seven-segment interface displayed a count of 3. Additional input sequences were also checked manually, as recorded in the project documentation.

## Debugging note
During testing, the FSM detection output was correct, but the seven-segment display showed incorrect values. Logic probes showed that the counter's binary outputs were correct. The issue was the bit ordering at the display interface: the counter outputs had been connected to the display inputs in the wrong order. Correcting the connections resolved the display mismatch.

## Files
- `Proteus/level_1.pdsprj` — Proteus project package.
- `Images/circuit.png` — schematic screenshot.
- `Documentation/project-notes.pdf` — project notes and design/debugging record.

## Tools and components
- Proteus 8 Professional
- 7474 D flip-flops
- 74LS163 counter
- Logic gates
- Seven-segment display
- DPATTERN input source

## Scope and limitations
This is a digital logic circuit implemented and simulated in Proteus. It is not a Verilog RTL implementation. The schematic could be made easier to inspect by improving signal labels and circuit layout.

## Author's note
This project was completed as an academic digital logic implementation. The repository documents the circuit, simulation and debugging process.
