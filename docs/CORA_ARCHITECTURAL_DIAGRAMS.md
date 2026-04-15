# CORA NPU: Architectural & Logic Blueprints

This document holds the core architectural logic diagrams that define the flow of the CORA native hardware and the Axiom OS stack.

## 1. The Physical Monolith Architecture
This diagram illustrates how the hardware subsystems on the custom BGA PCB route logic from the raw silicon to the human interface.

```mermaid
graph TD
    subgraph Power_Delivery_Network
        DC[12V DC Barrel Input] --> BUCK1[TPS54 5.0V Buck]
        DC --> BUCK2[TPS54 1.2V / 1.0V Bucks]
        DC --> BUCK3[TPS54 3.3V / 1.8V Bucks]
    end

    subgraph Memory_Array
        DDR[4GB DDR4 Microchip]
        SD[MicroSD Slot - Boot.bin]
    end

    subgraph The_Zynq_Engine_BGA
        PS[Processing System - ARM Cortex-A9]
        PL[Programmable Logic - Artix-7 FPGA]
        PS <-->|High-Speed AXI Interconnect| PL
    end

    subgraph The_Human_Interface
        HDMI[ADV7511 HDMI Encoding]
        USB[USB 2.0 PHY - Keyboard]
        TYPEC[FT232H Type-C Diagnostic Sentinel]
    end

    BUCK2 -->|1.0V/1.2V Core| The_Zynq_Engine_BGA
    SD -->|Boot OS| PS
    PS <-->|DDR4 Bus| DDR
    
    PL -->|Raw Pixel Data| HDMI
    HDMI -->|100-ohm Diff Pair| OUT_MONITOR[Physical Monitor]
    
    USB -->|90-ohm Diff Pair| PS
    KEYBOARD[Mechanical Keyboard] -->|Typing| USB
    
    TYPEC -->|JTAG/UART Serial SSH| PS
    PHONE[Android Phone Debugger] <--> TypeC
```

## 2. The Axiom OS Boot Sequence (Bare-Metal)
How the custom Axiom OS fundamentally powers on without a generic BIOS.

```mermaid
sequenceDiagram
    participant Power as Power Button
    participant ROM as Zynq BootROM
    participant SD as MicroSD (BOOT.bin)
    participant RAM as DDR4 memory
    participant OS as Axiom OS Kernel
    participant HDMI as Physical Monitor

    Power->>ROM: 12V Applied. Hardware Init.
    ROM->>SD: Look for primary boot device
    SD-->>ROM: Found BOOT.bin (FSBL)
    ROM->>RAM: Load First Stage Bootloader
    RAM->>OS: Execute Axiom OS bare-metal Kernel
    OS->>OS: Configure FPGA Logic Gates
    OS->>HDMI: Initialize Framebuffer 
    OS-->>HDMI: Render ASCII Boot Animation & Terminal
```

## 3. The Neurosymbolic Data Flow
How Alexitha generates a proof and the physical NPU verifies it mathematically.

```mermaid
graph LR
    subgraph Generative_Layer
        PROMPT[User Math Prompt Input]
        ALEXITHA[Alexitha 7B LLM / 8 tok per sec]
        PROMPT --> ALEXITHA
    end

    subgraph Deterministic_Physical_Layer
        TENET[Tenet Truth Filter]
        FPGA[CORA NPU Logic Gates]
        ALEXITHA -->|Proposed Proof Output| TENET
        TENET -->|Physical Logic Check| FPGA
    end

    FPGA -->|True| VERIFIED[HDMI Output: Verified Truth]
    FPGA -->|False| HALT[HDMI Output: Axiomatic Failure]
```
