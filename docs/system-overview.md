# CORA System Overview

This page explains CORA in one pass: what it is, how the software stack flows into hardware, and where the appliance sits in the broader Axiom architecture.

## One-Line Summary

CORA is the physical execution appliance for the Axiom stack: a machine where the reasoning model, formal languages, operating system, bus layer, and NPU are designed as one system.

## Fast Diagram

```mermaid
flowchart LR
    A[Alexitha] --> B[Flux / Tenet]
    B --> C[Axiom OS]
    C --> D[AXI Bridge]
    D --> E[Custom NPU]
    E --> F[CORA Board]
```

## Layer By Layer

### 1. Alexitha

Alexitha is the native reasoning-model layer. It generates reasoning workloads that are meant to be constrained and executed within the Axiom stack rather than handed off to a generic cloud runtime.

### 2. Flux and Tenet

Flux provides the math-native programming layer. Tenet provides the strategic and verification-oriented logic layer. Together they define structured computation rather than unconstrained model output.

### 3. Axiom OS

Axiom OS acts as the appliance runtime. It is responsible for orchestration, execution control, and the operating environment in which CORA behaves like a dedicated reasoning machine rather than a general-purpose desktop.

### 4. AXI Bridge

The AXI bridge is the key software-to-hardware interface. It provides the low-overhead path between the processing system and the programmable logic where the NPU runs.

### 5. Custom NPU

The NPU is the compute core for the math-heavy path. In the current direction, that means FPGA-based prototyping on Zynq hardware with a longer-term path toward more specialized hardware.

### 6. CORA Board

The board is the physical substrate that turns the stack into an appliance. It is not just packaging around computation. It is part of the design thesis: the compute path, enclosure, I/O model, and visible hardware presentation all matter.

## Why This Matters

Most AI systems are stitched together from generic layers. CORA is an attempt to do the opposite: make the path from reasoning to execution legible, constrained, and physically grounded.
