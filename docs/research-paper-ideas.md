# CORA Research Paper Ideas

This document translates the existing CORA research direction, including its earlier SIERRA naming history, into a clearer paper strategy.

The key argument across all three papers is the same:

> vertical co-design across language, kernel/runtime, silicon, and model can create guarantees that no layer-local approach can achieve on its own.

That is the through-line. The three papers simply attack it from different research communities.

## Overview

| Paper | Working Focus | Best-Fit Community |
|---|---|---|
| Paper 1 | Hardware-enforced AI safety | AI safety, ML systems, governance-adjacent safety |
| Paper 2 | CORA NPU architecture | computer architecture and accelerators |
| Paper 3 | Flux type theory | programming languages and formal methods |

## Paper 1: Hardware-Enforced AI Safety

### Working Title

**Beyond Guardrails: The Case for Hardware-Level Constraint Enforcement in Safety-Critical AI Systems**

### Core Thesis

Most AI safety work lives at the software layer: training-time alignment, prompt-time guardrails, output filters, retrieval layers, or monitoring systems. All of those can reduce risk, but they remain bypassable because they sit above the execution substrate.

This paper argues for a stronger framing: push safety constraints down the stack until they become structural rather than advisory.

In the Axiom/CORA framing, that means:

- `Flux` enforces semantic and type-level constraints at compile time
- `Tenet` enforces logical and runtime constraints below the application layer
- `SIERRA/CORA` enforces execution-level admissibility so only verified instruction paths reach the NPU

The central claim is that unsafe behavior should be made physically impossible where possible, not merely statistically less likely.

### Why This Paper Matters

This is probably the most immediately publishable paper in the CORA orbit because the workshop version does not require finished hardware. The argument can already be made using Flux, Tenet, and the CORA architecture as the reference system.

### Best-Fit Venues, Ranked

These are my fit-based recommendations from strongest to more fallback or adjacent options.

1. `NeurIPS Safety Workshop`
2. `NeurIPS`
3. `FAccT`
4. `SaTML`
5. `ICLR`
6. `ICML`
7. `AIES`
8. `AAAI`
9. `USENIX Security`
10. `IEEE S&P`

### Venue Notes

- `NeurIPS Safety Workshop` is the best first landing spot because it lets the argument enter the safety conversation before the hardware is fully mature.
- `NeurIPS` is the strongest flagship destination if the evaluation becomes sharp enough.
- `FAccT` is excellent if the paper leans into accountability, governance, and deployment implications for high-stakes settings.
- `SaTML` is a strong community fit if the paper becomes more explicitly safety-and-trustworthiness focused rather than pure ML novelty.
- `USENIX Security` and `IEEE S&P` become more plausible if the framing shifts from "AI safety" toward "enforcement architecture" and "unbypassable execution constraints."

## Paper 2: CORA NPU Architecture

### Working Title

**SIERRA: A Custom Neural Processing Unit Co-Designed with a Formally Constrained AI Reasoning Language**

If the public naming matters more later, this can become:

**CORA: A Neural Processing Appliance Co-Designed with a Formally Constrained AI Reasoning Stack**

### Core Thesis

Most NPUs and GPUs are designed independently from the reasoning language and software stack that eventually run on them. CORA rejects that split.

This paper's argument is that the ISA, compiler constraints, runtime assumptions, and hardware execution path were co-designed as one system:

- the hardware is not merely "accelerating AI"
- the ISA is shaped by what Flux can validly emit
- the runtime path is shaped by Tenet and Axiom OS
- the appliance architecture is shaped by Alexitha's reasoning workload and the desire for structural constraint enforcement

That is a stronger claim than "here is an accelerator with better throughput." It is a co-design paper.

### Why This Paper Matters

This is the architecture paper with the most prestige upside, but it is less immediate than Paper 1 because it benefits heavily from physical measurements, reproducibility, and implementation depth.

### Best-Fit Venues, Ranked

1. `ISCA`
2. `MICRO`
3. `ASPLOS`
4. `HPCA`
5. `FCCM`
6. `FPGA`
7. `DAC`
8. `DATE`
9. `PACT`
10. `IISWC`

### Venue Notes

- `ISCA` is the ideal flagship venue if the implementation and evaluation are compelling enough.
- `MICRO` is the closest fallback and still a top-tier architecture destination.
- `ASPLOS` becomes especially attractive if the paper emphasizes the language, runtime, and systems co-design angle rather than pure hardware novelty.
- `FCCM` and `FPGA` are particularly strong if the first truly convincing version of the system is FPGA-grounded and implementation-heavy.
- `DAC` and `DATE` become attractive if the story leans more toward design methodology, board realization, and hardware-system integration.

## Paper 3: Flux Type Theory

### Working Title

**A Type-Theoretic Foundation for Hallucination-Free Numerical Reasoning in Large Language Models**

### Core Thesis

This paper moves the argument into programming languages and formal methods.

The central claim is that numerical hallucination should not be treated as an empirical nuisance to be reduced with prompting tricks. It should be treated as a language-and-proof problem.

The Flux framing is that expressions with invalid numerical semantics should fail before execution:

- invalid reasoning should not merely be detected after the fact
- it should be made unrepresentable or unexecutable within the language
- the type system becomes part of the safety story

If developed rigorously, this paper becomes the formal foundation underlying the broader Axiom/CORA stack.

### Why This Paper Matters

This is probably the deepest theory paper of the three. It is intellectually powerful, but it also requires the most formal discipline: soundness claims, formal semantics, and theorem-level precision.

### Best-Fit Venues, Ranked

1. `POPL`
2. `LICS`
3. `PLDI`
4. `ICFP`
5. `OOPSLA`
6. `ESOP`
7. `CPP`
8. `FSCD`
9. `PEPM`
10. `TYPES`

### Venue Notes

- `POPL` is the strongest flagship destination if the type-theoretic story is genuinely foundational.
- `LICS` is a particularly good fit if the work becomes more logic-heavy and proof-oriented.
- `PLDI` becomes more plausible if the emphasis shifts toward practical language design and implementation.
- `ICFP` is attractive if the paper leans functional, expressive, and language-centric.
- `CPP`, `FSCD`, `PEPM`, and `TYPES` are strong adjacent communities for formalization-heavy or intermediate-stage work.

## Key Through-Line

All three papers make the same deeper argument:

- software-only fixes are not enough
- guarantees get stronger as constraints move downward
- vertical co-design across language, runtime, silicon, and model enables stronger assurances than any one layer can provide alone

Paper 1 is the easiest to draft soonest.

Paper 2 is the most architecture-prestigious if the hardware evidence becomes strong.

Paper 3 is the deepest formal foundation, but also the one that demands the most theorem-level rigor.

## Recommended Order

If the goal is momentum, credibility, and publishability:

1. Draft `Paper 1` first.
2. Build toward `Paper 2` as the hardware matures.
3. Develop `Paper 3` carefully as the formal backbone.

That sequence creates a strong progression:

- first the safety thesis
- then the hardware instantiation
- then the formal language foundation

## Source Trail

This document draws directly from the existing ideas already present in:

- `docs/neurips_hardware_safety_paper.md` in the main Axiom repo
- `paper_ideas.md` in the main Axiom repo
- `docs/CORA_PRD.md`
- `docs/CORA.md`

The wording here is intentionally recast for clarity, positioning, and venue strategy.
