# CORA Process Overview

This document maps the overall CORA build process at a high level.

It is intentionally phase-oriented rather than deeply technical. The goal is to show the full journey from concept to functioning appliance without turning this page into a detailed execution manual for each subsystem.

## Why This Exists

CORA spans multiple disciplines at once:

- product definition
- system architecture
- PCB design
- enclosure design
- embedded / OS integration
- hardware validation

Without a phase map, it is easy for the project to feel like one giant undefined effort. This document breaks the work into understandable stages.

## Phase 1: Thesis and Product Definition

This phase defines what CORA is and what it is not.

Key outcomes:

- define CORA as a sovereign reasoning appliance
- define the relationship to Axiom Lab, Flux, Tenet, Alexitha, and Axiom OS
- define the product story, use cases, and design language
- define the non-goals so the project does not drift into "generic AI box" territory

## Phase 2: Architecture Definition

This phase translates the thesis into a system architecture.

Key outcomes:

- choose the prototype hardware direction
- define the software-to-hardware execution path
- define the main board subsystems
- define interconnect assumptions
- define what must be local, what must be verifiable, and what must remain inspectable

## Phase 3: PCB Design

This phase turns the architecture into an actual board plan.

Key outcomes:

- schematic capture
- PCB layout and stack-up planning
- connector strategy
- power-delivery planning
- memory and interface placement
- board outline and mounting strategy

Tooling direction:

- board work is centered on `KiCad`

## Phase 4: Enclosure and Mechanical Design

This phase turns the board into a real physical object.

Key outcomes:

- 3D CAD model of enclosure and assembly
- standoff and mounting logic
- panel geometry
- cable access and connector fit
- physical design validation against the transparent monolith concept

This is also the phase where heat and thermal management must stop being abstract and become physical design constraints.

## Phase 5: Prototype Fabrication

This phase produces the first serious physical hardware iteration.

Key outcomes:

- fabricated PCB
- populated board or bring-up platform
- fabricated enclosure parts
- initial assembled unit

The point here is not perfection. The point is to get to a testable object as early as possible.

## Phase 6: Bring-Up and Integration

This phase is where the subsystems begin behaving like one machine.

Key outcomes:

- power-up validation
- boot-path validation
- debug-path validation
- display output validation
- keyboard/input validation
- first successful software-to-hardware execution path

This is usually where hidden assumptions surface fastest.

## Phase 7: Thermal, Mechanical, and Reliability Validation

This phase answers the question: does the appliance work consistently outside the lab narrative?

Key outcomes:

- thermal testing under load
- connector and cable reliability checks
- enclosure fit and stress checks
- repeated boot and run testing
- serviceability observations

This phase is especially important for CORA because visual enclosure ambition and thermal reality have to coexist.

## Phase 8: Team and Execution Scaling

This phase recognizes a practical truth: as CORA matures, the work stops being purely conceptual and starts requiring more specialized contributors.

Key outcomes:

- identify missing roles
- define ownership boundaries
- build the hardware, FPGA, embedded, and mechanical support structure
- shift from founder-led architecture definition to founder-led execution program

## Phase 9: Public Demonstration and Research Output

This phase turns internal progress into external proof.

Key outcomes:

- demonstrable appliance behavior
- public documentation
- benchmark and validation evidence
- paper submissions
- stronger narrative for partners, collaborators, and funders

## Phase 10: Iteration

No first version will be the final version.

The goal after the first integrated appliance is to iterate:

- revise the board
- revise the enclosure
- improve thermals
- tighten the software-hardware path
- clarify what belongs in the next revision of CORA

## Practical Summary

The overall process is:

1. define the thesis
2. define the architecture
3. design the board
4. design the enclosure
5. fabricate
6. integrate
7. validate
8. scale execution
9. demonstrate publicly
10. iterate

That is the full shape of the effort, even if several of those phases are still in front of the project today.
