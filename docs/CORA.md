# CORA
## Core Operating & Reasoning Appliance

**An Axiom Hardware Project**

---

## What CORA Is

CORA is the physical hardware manifestation of the Axiom computing paradigm. It is a custom-designed Neural Processing Unit (NPU) — a bare-metal AI accelerator — built from the logic gate level up, purpose-built to run Axiom OS natively and execute Flux-compiled mathematical reasoning at silicon speed.

It is not a GPU you buy from a vendor. It is not a server you rent from a cloud provider. It is not a laptop running Linux with a Python script calling OpenAI's API. CORA is a completely self-sovereign, air-gapped computing appliance that you physically designed, architect, and own at every layer of the stack.

When CORA is powered on, the only intelligence inside it is the intelligence you built:
- **Axiom OS** boots directly on the ARM processor embedded in the silicon.
- **Flux** — your domain-specific language for zero-hallucination mathematical reasoning — compiles its operations into a custom Instruction Set Architecture (ISA) you designed.
- **Your custom NPU logic** — flashed directly onto the FPGA fabric — physically reconfigures its logic gates to become the exact matrix computation engine your architecture specifies.
- **Alexitha** — your fine-tuned reasoning model — runs inference in a closed loop, natively, without any external dependencies.

Nothing on CORA was built by NVIDIA. Nothing was designed by Intel. No layer of its execution stack calls home to a cloud server. The entire vertical — from the physical silicon to the reasoning layer of the AI — is engineered by one person.

---

## The Technical Architecture

CORA's physical implementation is built on  the **Xilinx Zynq-7000** System-on-Chip (SoC). This chip is remarkable because it places two entirely different computational paradigms on a single piece of silicon:

1. **The Processing System (PS):** A dual-core ARM Cortex-A9 processor. This is the CPU that boots Axiom OS. It handles orchestration, memory management, user interaction through the HDMI terminal, and compilation of Flux programs.

2. **The Programmable Logic (PL):** A dense bed of Field-Programmable Gate Array (FPGA) logic fabric. This is the physical canvas onto which your custom NPU architecture is flashed. When Axiom OS boots, it loads a bitstream — a file that physically reconfigures the FPGA's internal logic gates — turning raw silicon into the exact matrix computation engine specified by your Verilog architecture.

These two halves communicate through the **AXI Bus**: a high-speed internal bridge connecting the ARM CPU and the FPGA fabric on the same chip. When Axiom OS needs to compute a matrix multiplication for an AI inference step, it doesn't send data across a PCIe cable to a foreign GPU. It writes tensor data to a specific memory address, and the FPGA NPU reads it directly from that address in nanoseconds, computes the result in parallel across its logic gates, and writes the answer back. The latency is near zero. The overhead is zero. It is the purest possible form of hardware-software co-design.

### The NPU Core

The heart of CORA's FPGA logic is a **Systolic Array** — the same fundamental architecture used in Google's Tensor Processing Units (TPUs). A systolic array is a grid of Processing Elements (PEs), each performing a multiply-accumulate (MAC) operation. Data flows rhythmically through the grid like a heartbeat, with each PE passing partial results to its neighbors. The result is massive parallelism: hundreds of simultaneous multiply-and-add operations happening in a single clock cycle.

CORA's NPU is specifically optimized for:
- **8-bit Integer Math (INT8):** The ALU (Arithmetic Logic Unit) natively operates in 8-bit arithmetic, matching the quantized precision of Alexitha's model weights.
- **Matrix Streaming:** The Axiom kernel streams model weight tensors from DDR4 RAM through the AXI bus directly into the systolic array, sustaining continuous inference without idle cycles.
- **Flux ISA Execution:** The Flux compiler's backend emits a custom instruction set targeting the NPU's control unit, allowing Flux programs to dispatch hardware-accelerated computation with zero software abstraction overhead.

---

## The Software Stack

| Layer | Component | Description |
|---|---|---|
| **Reasoning Model** | Alexitha | Fine-tuned Qwen 2.5 7B, zero-hallucination math reasoning |
| **Reasoning Language** | Flux | Custom DSL with formal semantics, constraint enforcement via Tenet |
| **Operating System** | Axiom OS | Custom kernel, initramfs, and boot pipeline for AI-native execution |
| **Hardware Driver** | AXI Bridge Driver | C kernel driver mapping ARM memory space to FPGA NPU fabric |
| **Hardware Logic** | CORA NPU | SystemVerilog systolic array flashed to Zynq FPGA fabric |
| **Physical Silicon** | Xilinx Zynq-7000 SoC | Dual ARM core + FPGA fabric on a single die |

---

## The Physical Design

CORA is not designed to be hidden. It is designed to be seen.

The entire philosophy of CORA's encasing is a direct rejection of the commodity black box. Most computers are designed to conceal their hardware — the assumption being that the hardware is someone else's work and not worth looking at. CORA inverts this entirely. Because you designed the silicon logic yourself, the hardware *is* the art. The encasing is built to make that visible.

### The Enclosure

CORA lives inside a **solid acrylic block enclosure**, constructed from six precisely CNC-machined or laser-cut panels of **10mm to 15mm thick optical-grade clear acrylic**. The thickness is deliberate — thin acrylic looks cheap and plastic. At 15mm, acrylic takes on the visual weight and optical clarity of glass. The edges catch and refract ambient light, creating a subtle prismatic glow around the boundary of the block.

The six panels are held together not by clips or cheap plastic fasteners, but by **four solid stainless steel standoffs** — one at each corner. These are knurled or sandblasted for grip and texture. They protrude slightly above and below the top and bottom panels, giving the enclosure the appearance of a precision instrument rather than a consumer device. The standoffs are the signature visual element: industrial, permanent, and unmistakably intentional.

Inside this glass-like structure, suspended in the center, is the **CORA carrier board**: a custom PCB (or the PYNQ-Z2 development board in the prototype phase) with:
- **Matte black solder mask** — not the standard glossy black, but a flat, light-absorbing matte finish.
- **ENIG surface finish (Electroless Nickel Immersion Gold)** — all exposed copper traces and pads are plated in 24-karat gold. The gold traces radiate outward from the central Zynq SoC like circuitry in a technical diagram made real.
- **Silk-screened "CORA" on the board itself**, in a clean monospaced typeface, just below the central SoC.

### The Status Indicator

A single **LED** is mounted on the board, visible through the acrylic enclosure. It serves as the only active visual feedback the enclosure provides:

- **Solid blue:** Axiom OS booted and idle.
- **Slow pulse:** Flux program in compilation.
- **Fast pulse:** NPU active — matrix computation in progress.
- **Off:** Powered down.

There are no screens on the enclosure itself. No unnecessary ports. No branding beyond "CORA" etched into the PCB. The minimalism is intentional.

### The Display Setup

CORA is an **air-gapped, offline appliance**. It does not connect to the internet. It does not connect to your laptop. Its sole interface with the outside world is:

1. **One HDMI cable** — routed to a dedicated monitor. Axiom OS renders its terminal interface directly to the framebuffer over HDMI. No desktop environment. No windows, no cursor. A high-contrast, monospaced terminal that fills the entire screen — white text on absolute black, or amber on black, depending on configuration. It looks like a command center, not a desktop.
2. **One USB cable** — connected to a mechanical keyboard. This is your only input device.
3. **One power cable** — into the wall.

That is the complete physical setup. Three cables. One glass box. One monitor. One keyboard. Total computational sovereignty.

### Enclosure Materials & Sourcing

| Component | Material | Source |
|---|---|---|
| Side panels × 6 | 15mm optical-grade clear acrylic | SendCutSend (laser cut) or Xometry (CNC) |
| Corner standoffs × 4 | Stainless steel, knurled | McMaster-Carr |
| Carrier PCB | Matte black solder mask, ENIG gold finish | JLCPCB or PCBWay |
| Status LED | Single 3mm blue LED | Onboard component |

**Estimated enclosure cost (prototype):** ~$130 CAD

---

## Why CORA Matters

Every AI company in the world right now is fighting over NVIDIA GPU allocation. They are writing Python on top of CUDA on top of Linux on top of Intel CPUs. They are entirely dependent on hardware they didn't design, running software they didn't write, managed by an operating system built for general-purpose computing and retrofitted for AI.

CORA is the opposite of that paradigm.

CORA is what happens when a single engineer refuses to accept any external dependency and builds the entire vertical themselves — the reasoning language, the operating system, the hardware architecture, and the physical silicon it executes on. It is not the most powerful AI accelerator in the world. It is the most intentional one.

It is proof that the future of AI compute does not have to belong exclusively to companies with billion-dollar chip fabrication budgets. It can be carved out, logic gate by logic gate, by one person who understands every layer of the machine they are building.

---

*CORA — Core Operating & Reasoning Appliance*
*An Axiom Project*
