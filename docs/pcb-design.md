# CORA PCB Design

This page explains the current PCB direction for CORA: what the board is meant to do, how it will be designed, and which major components are expected to appear on it.

## Current Status

The PCB is still in the design-definition phase, not final production.

The direction is clear, but the board should still be understood as an evolving hardware design rather than a frozen manufacturing package.

## Design Tooling

The CORA board is being designed in `KiCad`.

That matters for a few reasons:

- `KiCad` keeps the board files open and editable without vendor lock-in
- it is well-suited for schematic capture, PCB layout, stack-up planning, and manufacturing export
- it supports the staged workflow CORA needs right now: ideation, architecture definition, routing iteration, and later fabrication handoff

The current hardware files in this repo reflect that direction:

- `hardware/CORA_CARRIER_V1.kicad_sch`
- `hardware/CORA_CARRIER_V1.kicad_pcb`
- `hardware/CORA_CARRIER_V1.kicad_pro`

## Board Intent

The CORA PCB is not meant to be a generic development breakout. It is intended to become the carrier and integration point for the appliance:

- compute
- memory
- display output
- keyboard/input
- debugging
- boot storage
- power delivery

The board is also part of the visual identity of the product, not just its electrical substrate.

## Physical Direction

The board design language follows the broader CORA aesthetic:

- matte-black solder mask
- exposed ENIG finish where appropriate
- deliberate, clean routing
- a layout that looks intentional inside the transparent enclosure

This is both an engineering and product decision. The board has to work electrically, but it also has to feel like it belongs inside the "transparent monolith" design language described elsewhere in the repo.

## Major PCB Components

The table below describes the major board-level components and why they matter. Some part numbers may change as the design matures, but these are the important system roles the board must support.

| Component / Subsystem | Example Part / Direction | Why It Exists |
|---|---|---|
| Main compute SoC | Xilinx Zynq-7000 series | Provides the ARM processing system plus FPGA fabric, allowing Axiom OS orchestration and NPU logic on the same platform |
| FPGA / NPU execution path | Implemented in programmable logic on the Zynq fabric | Hosts the custom compute path used for CORA's hardware-accelerated reasoning and matrix execution |
| DDR memory | High-speed DDR memory placed close to the SoC | Holds model weights, runtime buffers, and working memory needed for local reasoning workloads |
| Power regulators / PDN | Buck converters and supporting power circuitry | Generates stable rails for logic, memory, I/O, and fabric so the board remains electrically reliable under load |
| HDMI output path | HDMI transmitter or equivalent video-output path | Allows CORA to boot into a dedicated display without depending on a conventional desktop GPU setup |
| USB host interface | USB PHY and Type-A or equivalent keyboard path | Supports direct keyboard input for the appliance-style interaction model |
| Debug / telemetry interface | USB-C, UART, FTDI, JTAG, or similar debug path | Gives the project a practical way to inspect boot behavior, collect logs, and debug low-level hardware/software integration |
| Boot storage | MicroSD or eMMC | Stores boot artifacts, the Axiom OS boot path, and the system image required to start the appliance |
| Clocking circuitry | Oscillator / clock source and supporting timing components | Provides stable timing for the SoC, memory, and peripheral interfaces |
| Reset / supervision circuitry | Reset controller, power-good logic, support components | Ensures the board starts cleanly and predictably during bring-up |
| Connectors | HDMI, USB, power input, debug headers | Exposes the minimal but necessary external interface of the CORA appliance |
| Passive support network | Resistors, capacitors, inductors, termination components | Supports signal integrity, decoupling, filtering, pull-ups/pull-downs, and stable subsystem operation |
| Mechanical mounting features | Standoff locations, board outline, enclosure alignment points | Lets the PCB physically integrate with the acrylic enclosure and the visible industrial design |

## Why These Components Matter Together

What makes CORA different is not any single chip by itself. It is the way the board brings the full stack together:

- local compute
- hardware-accelerated execution
- appliance-style I/O
- explicit debug paths
- physical integration with the enclosure

The PCB is the place where CORA stops being just a software story and starts becoming a machine.

## What Will Change

As the board matures, the following details may evolve:

- exact component selection
- memory capacity and topology
- debug-port strategy
- power-delivery implementation
- connector layout
- stack-up and routing constraints

That is normal. The role of this document is to define the board architecture and component logic clearly even while the specific implementation is still being refined.

## Relationship To Other Docs

- [hardware-status.md](hardware-status.md) explains where the hardware effort stands overall
- [CORA_CARRIER_ARCHITECTURE.md](CORA_CARRIER_ARCHITECTURE.md) goes deeper on system-level architecture
- [design-language.md](design-language.md) explains the visual and physical philosophy around the board
