# SIERRA NPU: The Mathematical Constraints & Calculations

Designing a bare-metal System-on-Chip board requires absolute mathematical precision. Before routing copper in KiCad, the physical constraints of the board must be calculated mathematically. Here is the master list of all calculations required for the SIERRA project:

## 1. Neurosymbolic Token Throughput (Memory Bandwidth)
The fundamental bottleneck of Large Language Models on edge hardware is not compute (FLOPs), but memory bandwidth. Every token generation requires the entire model weight to be read from RAM.
*   **Target Calculation:** Tokens per second ($$T_{speed}$$)
*   **Formula:** $$T_{speed} = \frac{\text{Memory Bandwidth (GB/s)}}{\text{Quantized Model Size (GB)}}$$
*   **SIERRA Variables:**
    *   Alexitha 7B (4-bit quantization) $\approx$ 3.5 GB
    *   Target Bus: DDR4 32-bit width at 2400MT/s $\approx$ 9.6 GB/s
    *   Theoretical raw read limit: ~2.7 iterations/sec.
*   **The Math to Solve:** We must calculate the exact cache-hit ratio using the Artix-7 FPGA BRAM to pipeline the matrix multiplication, boosting the raw read limit of 2.7 up to your target of **8 tokens/sec**.

## 2. High-Speed Routing (Impedance & Length Matching)
For the OS terminal to output to HDMI without destroying the video signal, the copper traces on the PCB must act as perfect transmission lines.
*   **HDMI Differential Impedance:** Must equal exactly $100 \Omega \pm 10\%$.
    *   **The Math to Solve:** Use trace width ($W$), trace gap ($S$), and dielectric height ($H$) over the prepreg layer in the KiCad impedance calculator to hit exactly 100 ohms.
*   **USB Data Impedance:** Must equal exactly $90 \Omega \pm 10\%$.
*   **Trace Length Matching Tolerances:**
    *   For the DDR4 RAM modules, the clock traces ($CK/CK\#$) and data traces ($DQ$) must be perfectly length-matched. 
    *   **The Math to Solve:** Calculate the picosecond delay of signals traveling over FR4 fiberglass (roughly 160 ps/inch) and tune the "squiggly" lines in KiCad to keep the timing skew below $\pm 10$ ps.

## 3. Power Delivery Network (Voltage Droop & Decoupling)
When the Zynq FPGA powers on its MAC units to do matrix multiplication, it can violently spike the current draw from 1 Amp to 8 Amps in a microsecond.
*   **Voltage Droop Tolerance:** The FPGA core ($V_{CCINT}$) runs at 1.0V. It cannot drop below 0.95V, or the math fails.
*   **Decoupling Capacitor Math ($C_{bypass}$):** 
    *   **Formula:** $C = \frac{I_{transient} \times \Delta t}{\Delta V}$
    *   **The Math to Solve:** Calculate the exact Farad value of ceramic capacitors needed directly underneath the Zynq BGA on the bottom layer to act as instantaneous power reserves.

## 4. FPGA Compute Limits (DSP Slices)
To achieve LLM inference locally, we are mapping the matrix multiplications hardware-level into the FPGA.
*   **Variables:** 
    *   Total DSP Slices on Artix-7 fabric (e.g., 220 slices).
    *   Total BRAM available (e.g., 4.9 Megabits).
*   **The Math to Solve:** Hardware resource allocation percentage. What percentage of logic is spent on the HDMI framebuffer vs. the neural net matrix multiplication arrays?
