# CORA V1 Prototype Plan

This document defines the fastest credible path to the first bootable physical CORA prototype.

`V1` is the version that makes CORA undeniable as a real, booting object.

It is not the final forever-version of CORA. It is the first serious, physical, bootable, photographed, demonstrated unit.

## What V1 Is

`CORA V1` is:

- a real physical prototype
- a transparent monolith enclosure around the current CORA hardware direction
- a Zynq-7000-based prototype path
- a strong enough object for grants, demos, photos, videos, and internal momentum
- a version that reaches a real first boot milestone

## What V1 Is Not

`CORA V1` is not:

- a production-ready hardware appliance
- a fully custom final board revision
- a thermally perfected final industrial design
- the last mechanical revision

The goal is not perfection. The goal is a first physical CORA that proves the thesis can become a machine.

For V1, that means CORA should not only exist as a shell. It should power on and reach a visible boot state.

## V1 Objective

Build the first bootable physical CORA prototype as quickly as possible after design lock, using the current architecture and sourcing direction already established in the repo.

## Core V1 Strategy

The V1 path should optimize for speed, legibility, and first boot:

1. lock the CAD
2. outsource the acrylic enclosure
3. source the visible stainless hardware
4. use the existing Zynq-7000 prototype path
5. assemble a real unit quickly
6. reach a visible and repeatable first boot path

That means V1 should be built around the current development-board path rather than waiting for a fully mature custom carrier board.

## Design-Lock Assumption

This plan assumes the design is locked on:

- `Friday, April 10, 2026`

That is the anchor date for the timeline below.

## Target V1 Window

If the design is truly locked on `Friday, April 10, 2026`, the most realistic V1 target window is:

- `Friday, April 17, 2026` to `Friday, April 24, 2026`

That is the window for a first assembled, photographed, boot-capable CORA.

## What "Boot" Means For V1

For V1, "boot" should be defined clearly and conservatively.

The minimum acceptable V1 boot state is:

- power is applied successfully
- the board starts consistently
- the display path comes alive over `HDMI`
- CORA reaches a visible terminal or boot screen associated with the intended runtime path

The ideal V1 boot state is:

- repeatable boot into an `Axiom OS` terminal or clearly branded transitional runtime
- visible status indication
- keyboard input path at least partially recognized

V1 does not need to prove the full final CORA software stack. It does need to prove that CORA is a booting appliance rather than only an enclosure around hardware.

## V1 Timeline

### Friday, April 10, 2026

- lock enclosure geometry
- lock panel dimensions
- lock standoff positions
- lock connector cutout assumptions
- finalize the Fusion concept assembly
- generate clean fabrication-ready files

### Saturday, April 11 to Sunday, April 12

- run the focused weekend sprint
- finish render pack
- verify clearances
- verify port exposure
- confirm standoff family and hardware assumptions
- prepare the procurement package
- confirm the boot-path assumptions for the dev-board route

### Monday, April 13

- submit acrylic fabrication request
- order stainless standoffs and matching fasteners
- confirm the Zynq-7000 prototype-board path
- order any missing bring-up accessories
- define the minimum boot image and display setup needed for first power-on

### Tuesday, April 14 to Thursday, April 16

- finalize the V1 assembly instructions
- prepare the visual concept sheet
- prepare documentation for assembly and demonstration
- pre-stage the software / OS side as much as possible
- prepare the boot medium, display path, keyboard path, and debug path

### Friday, April 17 to Wednesday, April 22

- expected earliest practical arrival window for enclosure and hardware parts
- dry-fit the structure
- verify mounting and connector alignment
- correct any simple mechanical issues
- pre-stage bring-up once the physical fit is confirmed

### Saturday, April 18 to Friday, April 24

- complete physical assembly
- complete first power-on and bring-up attempts
- reach first visible boot milestone
- photograph and render the built unit
- produce the first real CORA demo artifact set

## V1 Hardware Direction

### Compute Path

V1 should use:

- `Zynq-7000-based prototype hardware`

That keeps the project moving while the more custom board path matures, and it is the fastest route to a real first boot.

### Enclosure Path

V1 enclosure direction:

- `optical-grade clear acrylic`
- target visual thickness: `15 mm` where feasible
- if fast ordering favors a thinner stock path, use the closest acceptable heavy clear acrylic option for V1 and preserve the fuller monolith target for V2

### Structural Hardware

V1 should use:

- `4 stainless-steel corner standoffs`
- sourced from `McMaster-Carr`

These are part of the object identity, not just internal hardware.

### Board / Visual Direction

The visible internal direction should still reflect:

- matte-black board language where possible
- minimal visual clutter
- explicit internal structure
- visible seriousness

### Boot / Runtime Direction

V1 should target:

- first boot over `HDMI`
- visible terminal or boot-state output
- direct keyboard-driven interaction path where possible
- a debugable bring-up environment rather than a polished consumer UI

The fastest honest V1 is a bootable appliance prototype, not a fully polished product shell.

## V1 Procurement Summary

### Acrylic

Preferred sourcing direction:

- `SendCutSend` if the panel geometry is simple and the stock supports the visual goal
- `Xometry` if more thickness or machining flexibility is needed

### Standoffs And Fasteners

Preferred sourcing direction:

- `McMaster-Carr`

### Prototype Board Path

Use the current:

- `Zynq-7000 development-board path`

until a more custom board is ready.

## Actual Bottlenecks

In order of importance, the real V1 bottlenecks are:

### 1. Money

This is the clearest immediate bottleneck.

It covers:

- acrylic enclosure fabrication
- stainless standoffs and matching fasteners
- any missing development-board or bring-up hardware
- shipping speed

Once the design is locked, money becomes the main variable controlling how fast V1 turns into a physical object.

### 2. Design-Lock Discipline

If the geometry keeps moving, everything slows down:

- acrylic files cannot be submitted confidently
- standoff selection stays fuzzy
- cutouts stay unstable
- ordering gets delayed

V1 moves quickly only if the design is treated as locked once the final CAD is exported.

### 3. Vendor Lead Time

Even with money ready, the physical build depends on:

- acrylic fabrication lead time
- shipping time
- hardware delivery time

This is especially true for the enclosure path.

### 4. Boot-Path Readiness

If the software, `HDMI`, keyboard, and debug setup are ignored until the enclosure arrives, the next bottleneck appears immediately.

That means the boot image, display path, input path, and first bring-up assumptions should be prepared in parallel with the procurement process.

## V1 Rough Budget (CAD)

This section gives the rough V1 budget in Canadian dollars.

It is a planning budget, not a final quote.

### Budget Assumptions

- enclosure prototype estimate in the repo: about `130 CAD`
- development-board path may range depending on whether the board is already owned
- stainless hardware cost depends on final McMaster part selection
- shipping and customs can materially affect the fast-build path

### Core Cost Categories

| Category | Rough CAD Range | Notes |
|---|---:|---|
| Acrylic enclosure panels | `130-250 CAD` | `130 CAD` is the existing repo estimate; higher if `Xometry` or thicker machining path is used |
| Stainless standoffs + fasteners | `40-120 CAD` | depends on McMaster part family, finish, and shipping |
| Zynq dev-board path | `0-420 CAD` | `0` if already owned; otherwise roughly `200-420 CAD` depending on board path |
| Power / boot / bring-up accessories | `40-150 CAD` | power supply, cables, storage, keyboard/display adapters if needed |
| Shipping / customs / rush costs | `40-150 CAD` | varies heavily with vendor and timing |

### Budget Scenarios

#### Minimum V1 Budget

Use this if the development board and most bring-up gear are already in hand.

- acrylic: `130 CAD`
- standoffs / fasteners: `40-80 CAD`
- accessories / gaps: `40-80 CAD`
- shipping: `40-80 CAD`

Estimated total:

- `250-370 CAD`

#### Likely V1 Budget

Use this if you need a cleaner first prototype path with some missing hardware and moderate shipping.

- acrylic: `150-220 CAD`
- standoffs / fasteners: `60-100 CAD`
- accessories / gaps: `75-125 CAD`
- shipping: `60-100 CAD`

Estimated total:

- `345-545 CAD`

#### Full V1 Budget

Use this if you still need to acquire the development-board path as well.

- acrylic: `150-250 CAD`
- standoffs / fasteners: `60-120 CAD`
- Zynq dev board: `200-420 CAD`
- accessories / gaps: `75-150 CAD`
- shipping: `60-150 CAD`

Estimated total:

- `545-1,090 CAD`

## Best Read On The Budget

If the development board is already available, V1 is relatively affordable.

If the board still needs to be acquired, that becomes the largest single cost category.

So the cleanest summary is:

- `~250-370 CAD` if the board is already in hand
- `~545-1,090 CAD` if the board still needs to be bought

That is why money becomes the main bottleneck once design lock happens.

## V1 Deliverables

By the end of V1, CORA should have:

- one assembled physical unit
- one repeatable first-boot path
- one visible display-output path over `HDMI`
- one full render set
- one real photo set
- one clean concept sheet
- one short assembly / sourcing record
- one demo-ready story for grants and outreach

## V1 Bring-Up Requirements

To count as a real V1, the following bring-up components should be ready:

- power input path
- display connection
- keyboard connection
- boot medium or image path
- debug path for failures

Without these, V1 risks becoming only a physical shell.

## V1 Success Criteria

V1 is successful if all of the following are true:

- CORA exists as a physical object
- CORA powers on as an appliance
- CORA reaches a visible boot state
- the object clearly matches the Axiom thesis visually
- the enclosure feels intentional, not improvised
- the internal structure reads as serious hardware
- the object is strong enough for applications, features, and demos

The single most important success threshold is:

- someone can look at CORA on a desk, power it on, and see it boot

## V1 Risks

The most likely V1 risks are:

- connector cutout mismatch
- acrylic lead times
- fastener / standoff mismatch
- thermal assumptions becoming visible too late
- over-perfectionism slowing the build
- boot-path issues taking longer than enclosure work
- HDMI bring-up friction
- keyboard / input path not working on first try
- debugging overhead if the image path is not prepared early

## V1 Standard

The V1 standard is:

- not fabrication-final
- not fully mature
- but absolutely real
- and visibly alive

It should feel like the first undeniable CORA.

If V1 does not boot, it may still be a good mockup, but it is not the full V1 target described here.
