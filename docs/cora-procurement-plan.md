# CORA Procurement Plan

This document turns the existing CORA architecture and enclosure direction into a practical sourcing plan.

It is not a fabrication-final bill of materials. It is a procurement guide for:

- what already has a sourcing direction
- what should be purchased first
- what should wait until the design is more mature
- which vendors currently fit the CORA concept best

## Why This Exists

The repo already contains strong architectural and design direction for CORA, but that is not the same thing as having a usable buying plan.

This document answers the practical question:

What do we actually need to source, from where, and in what order?

## Procurement Philosophy

Right now, CORA should be sourced in layers:

1. lock the visual and mechanical concept
2. source the enclosure and visible structural hardware
3. source the prototype board / bring-up platform
4. source supporting debug, power, and display equipment
5. delay any fabrication-final purchasing until CAD and architecture stabilize

The immediate goal is not mass purchasing. The goal is a clean path from concept to serious prototype.

## Already Chosen Sourcing Direction

The current CORA docs already establish the following sourcing preferences:

- `Optical-grade clear acrylic` for the enclosure
- `Stainless-steel standoffs and fasteners` for the visible structural hardware
- `JLCPCB` or `PCBWay` for the carrier PCB when fabrication is ready
- a `Zynq-7000`-based prototype path for the compute platform

Those choices should remain the baseline unless the design changes materially.

## Enclosure Procurement

### Acrylic Panels

The chosen material direction is:

- `15 mm optical-grade clear acrylic`

This is the right fit for CORA because it:

- supports the transparent monolith concept
- gives the enclosure real visual weight
- reveals the internal board and structure
- feels architectural rather than hobbyist

The currently preferred vendors are:

- `SendCutSend`
  - good fit if you want clean cut acrylic panels from provided 2D fabrication files
  - strong option for early enclosure iteration if the geometry can be expressed cleanly
- `Xometry`
  - better fit if you want more flexible CNC-oriented fabrication options
  - useful if the geometry becomes more complex or you want broader manufacturing choice

### Recommendation

For the current phase:

- use `Fusion` to lock the panel geometry
- generate panel-by-panel fabrication files
- use `SendCutSend` first if the panels remain simple
- use `Xometry` if the enclosure evolves into something more mechanically complex

### Important Practical Constraint

The current fast-fabrication path may not perfectly match the full visual ideal.

In practical terms:

- `SendCutSend` is attractive for speed and simplicity
- but if the design truly requires a full `15 mm` monolith treatment, the project may need a more CNC-oriented path such as `Xometry`

That means the enclosure decision is partly a design decision and partly a speed decision.

### What Not To Order Yet

Do not order acrylic panels yet if:

- connector cutouts are still moving
- standoff hole positions are not final
- board dimensions are still changing
- thermal vent assumptions are still unresolved

At this stage, it is better to finalize the CAD than to rush the acrylic order.

## Structural Hardware Procurement

### The Four Metallic Corner Pieces

The four visible metallic elements are:

- `corner standoffs`

In CORA, these are not secondary hardware. They are part of the product identity.

They should be:

- `stainless steel`
- visually precise
- strong enough to hold the acrylic structure cleanly
- compatible with a serviceable assembly process

The current sourcing direction is:

- `McMaster-Carr`

Why McMaster-Carr:

- reliable mechanical hardware selection
- strong selection of stainless standoffs and fasteners
- easy to source matching hardware families
- good fit for a serious prototype build

### What To Look For

When sourcing the standoffs, prefer:

- stainless steel
- clean cylindrical or knurled appearance
- enough diameter to feel structural, not flimsy
- enough height to create a visible air gap and suspended-board aesthetic
- matching screws / threaded hardware from the same family when possible

These standoffs should visually read as:

- permanent
- engineered
- architectural

not:

- cheap spacers from a hobby kit

## PCB And Board Procurement

### Prototype Direction

For the current prototype stage, the compute path is centered on:

- `Xilinx Zynq-7000`

There are two procurement layers here:

1. an early prototype / bring-up platform
2. eventual custom carrier-board fabrication

### Immediate Compute Path

For the earliest serious prototype phase, the practical move is still:

- use a `Zynq-7000-based development board` as the bring-up path

This lets the project advance without waiting for the full custom board to be complete.

### Later Board Fabrication

When the carrier board is ready for fabrication, the current vendor direction is:

- `JLCPCB`
- `PCBWay`

These are the right vendors to keep in mind for:

- matte-black solder mask direction
- ENIG finish
- prototype board runs
- later iteration

### Do Not Rush

Do not place a fabrication order for the custom carrier board until:

- the architecture is stable enough
- the connector layout is more mature
- the power-delivery path is coherent
- the memory and debug strategy are clearer

## Supporting Prototype Equipment

The CORA prototype path also implies a small set of supporting equipment.

These are not all "CORA parts," but they are part of the real bring-up environment.

### Likely Supporting Items

- dedicated monitor with HDMI input
- mechanical keyboard via USB
- stable bench or wall power supply path
- debug cable / UART / JTAG tooling as needed
- measurement tools for power and thermal checks

These items should be sourced only to the level needed for effective bring-up, not overbuilt for appearance.

## Procurement Layers

### Layer 1: Buy Only After CAD Lock

- acrylic panels
- corner standoffs
- matching fasteners
- any visible enclosure hardware

### Layer 2: Buy For Prototype Execution

- Zynq-7000 prototype board if not already in hand
- power accessories
- debug accessories
- HDMI / input accessories

### Layer 3: Buy Later

- fabricated custom carrier PCB
- higher-fidelity enclosure revisions
- refined thermal hardware
- improved serviceability or production-oriented revisions

## Best Current Vendor Summary

| Item | Current Best Direction | Why |
|---|---|---|
| Acrylic enclosure panels | `SendCutSend` first, `Xometry` if geometry becomes more complex | Best fit for the transparent monolith enclosure path |
| Four metallic corner supports | `McMaster-Carr` | Strong source for stainless standoffs and matching fasteners |
| Custom carrier PCB | `JLCPCB` or `PCBWay` | Good prototype board fabrication path for matte-black / ENIG board direction |
| Early compute platform | `Zynq-7000 development-board path` | Best way to prototype before full custom board maturity |

## Immediate Weekend-Sprint Procurement Read

If the goal is a weekend sprint after the design is locked, the immediate actionable path is:

1. finish the `Fusion` model
2. finalize panel geometry and standoff assumptions
3. identify the exact standoff family on `McMaster-Carr`
4. prepare acrylic fabrication files for `SendCutSend`
5. confirm whether the prototype path uses an existing `Zynq-7000` dev board or requires acquisition

That is the correct level of sourcing for the next step.

## Procurement Bottlenecks

The procurement bottlenecks are not evenly weighted.

In order of importance, they are:

### 1. Money

Procurement only moves once there is enough cash to cover:

- acrylic fabrication
- structural hardware
- any missing dev-board path
- bring-up accessories
- shipping

### 2. Design Lock

If the geometry is still changing, procurement is still blocked.

### 3. Vendor Lead Time

Even after ordering:

- acrylic fabrication
- hardware shipping
- customs and delivery timing

can still slow the first build materially.

### 4. Bring-Up Readiness

Procurement alone does not finish V1.

If the boot image, `HDMI` setup, keyboard path, and debug path are not prepared in parallel, the bottleneck simply moves from purchasing to bring-up.

## Practical Summary

The current CORA procurement direction is already clear at a high level:

- `15 mm optical-grade clear acrylic`
  - source direction: `SendCutSend` or `Xometry`
- `4 stainless-steel corner standoffs`
  - source direction: `McMaster-Carr`
- `prototype / future board fabrication`
  - source direction: `JLCPCB` or `PCBWay`

The main thing still missing is not vendor direction. It is final-enough geometry and part selection to place orders confidently.
