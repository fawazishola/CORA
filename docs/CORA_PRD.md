# Product Requirements Document (PRD): CORA

## 1. Executive Summary
**Product Name:** CORA (Core Operating & Reasoning Appliance)
**Lead Architect:** Fawaz Ishola, Founder & Research Lead, Axiom Lab
**Date:** March 2026

**Vision:**
CORA is a "Full-Stack Sovereign" AI appliance. It is a neurosymbolic reasoning engine built entirely from the logic-gate level up. CORA rejects the modern paradigm of relying on generic commercial GPUs (NVIDIA) and rented cloud intelligence (OpenAI). Instead, it provides a completely air-gapped, vertically integrated computational monolith where the hardware (custom NPU), compiler (Flux), operating system (Axiom OS), and intelligence (Alexitha) are all proprietary, verifiable, and optimized for mathematical exactness.

**Target Market & Use Cases:**
- **Phase 1 (Internal Labs):** Edge-compute platform for Axiom Lab's proprietary neurosymbolic research and verifiable computation validation.
- **Phase 2 (B2B Infrastructure):** The backend silicon architecture that will eventually power the highly complex actuarial modeling and AI operations for the **Atlas** creator economy platform with zero-latency inference costs.
- **Phase 3 (High-Stakes Edge Compute):** Real-time telemetry, fluid dynamics, and race strategy logic processing for top-tier motorsports (WEC, Formula E, F1) and advanced fintech risk assessment. 

---

## 2. Hardware Architecture
The core computational engine abandons generic CPU/GPU abstractions in favor of a mathematically native logic flow.

- **Development Prototype:** Xilinx Zynq-7000 SoC (ARM CPU + FPGA Fabric) utilizing the PYNQ-Z2 development board.
- **NPU Design:** A custom Systolic Array implemented in SystemVerilog, flashed onto the FPGA fabric.
- **Data Bus:** High-speed AXI interconnects bridging the ARM processing system with the programmable FPGA logic.
- **The Carrier Board:** Transitioning from the green PYNQ-Z2 to a proprietary custom carrier PCB.
  - **Aesthetic:** Matte black solder mask.
  - **Traces:** Exposed ENIG (Electroless Nickel Immersion Gold) traces.
  - **Design Language:** Brutalist, hyper-organized, prioritizing signal integrity and visual perfection.

---

## 3. Physical & Industrial Design (The "Transparent Monolith")
The physical casing must reflect the philosophical purity of the software. It must not look like a consumer PC; it must look like an artifact of advanced intelligence.

- **The Enclosure:** 15mm thick optical-grade clear acrylic plates, creating a heavy, glass-like monolithic block.
- **Mounting:** Heavy-duty, industrial stainless-steel standoffs holding the acrylic plates and suspending the naked PCB in the center of the block.
- **Visibility:** No opaque plastics or cheap bezels. The matte black and gold PCB, the chips, and the routing must be completely visible from all angles.
- **Status Indication:** A single, minimalist status LED indicating NPU calculation load (e.g., pulsing during intense symbolic reasoning).

---

## 4. I/O and The "Sovereign" User Experience
CORA is a standalone appliance. It does not connect to a generic desktop environment. It dictates its own I/O paradigm.

- **Display Output (HDMI):** A direct, hardwired HDMI connection from the CORA board to a dedicated minimalist monitor.
  - **The Boot Sequence:** When powered on, the screen bypasses standard BIOS logos and boots instantly into the **Axiom OS Terminal**.
  - **The UI:** There is no generic desktop (no Windows, no Ubuntu GUI). The output is a high-contrast, perfectly monospaced command-line interface (e.g., amber, neon-cyan, or raw white on absolute pitch black). It is a pure sci-fi hacker’s console dedicated strictly to reasoning.
- **Input (USB/Mechanical Keyboard):** A single USB connection for a heavy, industrial-grade mechanical keyboard (ideally matching the monolithic acrylic/metal aesthetic, potentially featuring custom keycaps mapped to Flux language mathematical symbols).
- **Air-Gapped Sovereignty:** No Wi-Fi or Bluetooth antennas by default. The machine operates on pure internal local inference to ensure maximum security and privacy.

---

## 5. Software Stack Integration
CORA is the physical manifestation of the Axiom Lab software ecosystem.

- **Operating System:** **Axiom OS** (custom kernel and bootloader designed specifically to communicate with the AXI bus and the NPU fabric).
- **Compiler/Language:** **Flux** (a mathematically native domain-specific language) and **Tenet** (for verifiable smart-contract and state execution).
- **The Intelligence Model:** **Alexitha** acts as the native operating mind of the appliance, executing zero-hallucination logic directly on the NPU gates without the massive overhead of standard Python/PyTorch abstractions.

---

## 6. Development Milestones & Roadmap
- [x] **Milestone 1:** SystemVerilog NPU core (Systolic Array) simulated and synthesized for the PYNQ-Z2.
- [x] **Milestone 2:** Axiom OS bootloader and terminal environment configured.
- [ ] **Milestone 3:** Establish successful HDMI passthrough outputting the bare-metal Axiom OS terminal to a dedicated monitor.
- [ ] **Milestone 4:** Fabrication of the 15mm optical-grade acrylic "Transparent Monolith" case and steel standoff assembly.
- [ ] **Milestone 5:** Successful execution of a complex Flux script performing neurosymbolic mathematics via Alexitha natively on the CORA enclosed appliance.
- [ ] **Milestone 6:** Final PCB design of the custom matte-black/gold carrier board via KiCad/Flux.ai replacing the stock PYNQ-Z2 board layout.
