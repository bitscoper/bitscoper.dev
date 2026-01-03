---
date: "2025-03-01T13:56:47+00:00"
title: "Understanding Quantum Volume"
---

Quantum Volume is a performance metric used to evaluate the overall capabilities and error characteristics of quantum computers. It measures the **largest square-shaped quantum circuit**—in terms of both qubit count and circuit depth—that a given quantum computer can execute successfully.

The success of a benchmark is determined by specific criteria that assess whether a quantum computer has correctly executed a given circuit. While the structure of these benchmark circuits is independent of the underlying hardware architecture, compilers are free to optimize them to take advantage of the machine’s unique characteristics. This makes Quantum Volume a useful metric for comparing different quantum computing platforms.

Quantum Volume is particularly important because it accounts for the practical limitations of quantum computation. Although qubits resemble classical bits conceptually, they are highly susceptible to decoherence and operational errors. As a result, a smaller number of high-quality, low-error qubits can be more valuable than a larger set of noisy, unreliable ones.

The idea of **volumetric benchmarks** expands on Quantum Volume by considering not only square circuits but also rectangular ones. This broader approach enables a deeper examination of the trade-offs between circuit width (number of qubits) and circuit depth. By decoupling these two dimensions, volumetric benchmarks provide a more nuanced and realistic picture of how quantum computers perform under varying computational demands.
