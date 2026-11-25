---
layout: page
permalink: /research/
title: research
description: Combining the guarantees of deterministic defenses with the efficiency of AI to secure software against memory-safety vulnerabilities.
nav: true
nav_order: 2
---

Memory-safety vulnerabilities are the main source of serious failures and attacks in software. A defense against them must be deterministic: it must catch every violation, every time. Deterministic defenses are reliable but expensive, while AI tools are efficient but cannot yet give this guarantee. My research combines the two. My work moves step by step from traditional deterministic defense toward AI.

A full description is in my [research statement](/assets/pdf/Yubo_Du_Research_Statement.pdf).

---

### Part 1: Efficient deterministic defense

**Use-after-free prevention for deployed software — FPN (NDSS 2026).**
When a buffer is freed, a runtime defense must find and invalidate every pointer that still refers to it. Existing defenses track each pointer separately and can more than double a program's memory use. I found that pointers have strong locality: pointers stored at nearby addresses usually point to nearby addresses. FPN is, to the best of my knowledge, the first defense that uses pointer locality without weakening protection. It combines a coarse-grained record of which memory block points to which region with a fine-grained label that marks the exact locations to check. FPN reduces memory overhead from about 173% to about 8%, and runtime overhead from about 56% to about 18%, with the same protection on real-world vulnerabilities.
[[Paper]](https://www.ndss-symposium.org/wp-content/uploads/2026-f753-paper.pdf) [[Code]](https://github.com/duyubo/Fast-Pointer-Nullification-NDSS-2026)

**Use-after-free detection for testing — RTT (ICS 2024).**
Key-and-lock sanitizers detect use-after-free precisely, but they must propagate a large identifier with every pointer, which causes about two thirds of their overhead. RTT uses the number of times an address has been reused as the identifier. This number is small enough to fit in the unused upper bits of the pointer, so nothing needs to be propagated. RTT reduces runtime overhead by up to 7×, and memory overhead from more than 100% to under 8%, with the same detection rate.
[[Paper]](https://doi.org/10.1145/3650200.3656606)

### Part 2: Diagnostic vulnerability detection

**Out-of-bounds detection that explains itself — Witness (under review).**
To repair an out-of-bounds bug, a developer or an AI tool needs to know which buffer is involved and where the pointer first goes out of bounds. Existing sanitizers report only the faulting access, or they rerun the program or stop early to find the cause. Witness labels only the pointers that have already gone out of bounds and carries their bounds and formation site, so it reports the root cause in a single run without stopping the program.

### Part 3 (ongoing): Verifying the reasoning of AI

**Checking LLM vulnerability reasoning against program behavior (at CMU).**
LLMs can find memory-safety vulnerabilities, but they also report bugs that do not exist and miss bugs that do. I build a sanitizer-style checker that instruments every operation an LLM names in its explanation — the allocation, the free, each pointer copy — and compares the explanation with the recorded runtime behavior. This shows which reasoning steps are wrong, including hallucinated steps. We then use causal analysis to find which code patterns lead to these mistakes.

---

### Future directions

- **AI-guided selective protection.** Use AI and fuzzing to find the code an attacker can influence, and apply deterministic protection only there, within a performance budget.
- **AI-assisted migration to memory-safe languages.** Check the boundary between Rust and C/unsafe Rust at runtime, and verify code that AI translates from C to Rust.
- **Deterministic checking of AI-generated code.** Have AI tools state the expected behavior of their code, and check it with compiler instrumentation at runtime.
