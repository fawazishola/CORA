# CORA

Core Operating & Reasoning Appliance

CORA is Axiom Lab's hardware appliance for sovereign, verifiable AI computation. It combines a custom NPU architecture, Axiom OS, Flux, and Alexitha into a single air-gapped system designed for mathematical reasoning and zero-cloud execution.

Originally, the project was developed under the name `SIERRA` (Symbolic Intelligence Engine for Reasoning & Recursive Architecture). That name still appears in legacy architecture documents and board files across this directory.

## What CORA Is

CORA is not a generic AI workstation and it is not a rented GPU endpoint in a box. It is intended as a tightly integrated reasoning appliance where the software stack and the hardware execution model are designed together.

At a high level, CORA brings together:

- `Axiom OS` as the operating environment
- `Flux` as the math-native programming language
- `Tenet` as the strategic and verification layer
- `Alexitha` as the native reasoning model
- a custom NPU architecture built around FPGA-based prototyping and future custom hardware

## Why It Exists

Most AI systems are assembled from layers that were never designed for formal reasoning or verifiable execution. CORA takes the opposite approach: build a system where the reasoning language, execution environment, and hardware constraints reinforce each other.

The goal is not just speed. The goal is control, inspectability, and a stack whose behavior can be reasoned about from the software layer down to the silicon.

## Hardware Direction

The current prototype direction is centered on the Xilinx Zynq-7000 SoC:

- ARM processing system for orchestration and OS execution
- FPGA fabric for the NPU logic
- AXI interconnect for low-overhead communication between software and hardware
- custom carrier-board work for a distinct CORA physical design

The long-term design language is a visible, brutalist appliance:

- matte-black carrier board
- exposed ENIG traces
- acrylic enclosure
- dedicated HDMI terminal output
- minimal external I/O

## Repository Contents

This directory contains the hardware and architecture material for CORA:

- [CORA_PRD.md](/home/fawaz/Documents/Axiom/sierra/CORA_PRD.md) - product requirements and positioning
- [SIERRA.md](/home/fawaz/Documents/Axiom/sierra/SIERRA.md) - legacy long-form hardware narrative from the original naming
- [SIERRA_CARRIER_ARCHITECTURE.md](/home/fawaz/Documents/Axiom/sierra/SIERRA_CARRIER_ARCHITECTURE.md) - carrier-board and system architecture notes
- [SIERRA_ARCHITECTURAL_DIAGRAMS.md](/home/fawaz/Documents/Axiom/sierra/SIERRA_ARCHITECTURAL_DIAGRAMS.md) - diagrams and logic blueprints
- [SIERRA_MATH.md](/home/fawaz/Documents/Axiom/sierra/SIERRA_MATH.md) - engineering calculations and constraints
- KiCad project files for the carrier board and related hardware work

## Position in the Axiom Stack

| Layer | Component | Role |
|---|---|---|
| Application Logic | Flux / Tenet | Structured reasoning and verified computation |
| Model Layer | Alexitha | Native reasoning engine |
| OS Layer | Axiom OS | Appliance runtime and device control |
| Hardware Layer | CORA | Dedicated execution appliance |

## Current Status

CORA is in active architecture and prototyping mode. The repo already contains the product framing, hardware direction, and board-design groundwork, but the project is still evolving from research hardware into a unified appliance.

## Notes

- When you see `SIERRA` in filenames, read it as historical naming unless the file is explicitly about the older branding.
- If you want the naming fully normalized later, we can do a second pass across the `sierra/` directory and update legacy docs more broadly.
