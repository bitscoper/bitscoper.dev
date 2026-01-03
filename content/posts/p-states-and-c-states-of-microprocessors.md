---
date: "2025-02-20T21:44:13+00:00"
title: "P-states and C-states of Microprocessors"
---

Processor power management is defined by the **Advanced Configuration and Power Interface (ACPI)** specification and is primarily categorized into two mechanisms: **performance states (P-states)** and **idle sleep states (C-states)**.

## P-states (Performance States)

- **Function:** P-states reduce CPU power consumption by dynamically adjusting the processor’s **operating frequency and voltage**, allowing performance to scale based on workload demand.
- **Behavior:** When workloads are light, the CPU operates at lower frequencies and voltages; under heavy workloads, it transitions to higher-performance states.
- **Variability:** The number of available P-states varies by CPU model and microarchitecture, even within the same processor family.

P-states enable **power-efficient performance scaling** without fully idling the processor.

## C-states (Idle States)

- **Function:** C-states represent **idle power-saving modes** in which parts of the CPU are shut down when no work is being performed.
- **Depth:** Each deeper C-state (e.g., C1 → C6/C10) powers down more internal components, resulting in **greater power savings** but **higher wake-up latency**.
- **Visibility:** Not all supported C-states are necessarily exposed to the operating system; availability depends on **CPU design, firmware, and vendor implementation**.

C-states are optimized for conserving energy during idle periods.

## Key Differences

- **P-states:** Adjust performance while the CPU is active.
- **C-states:** Reduce power consumption when the CPU is idle by disabling internal functions.

In summary, **P-states manage performance efficiency**, while **C-states enable deeper power savings during inactivity**, together forming the foundation of modern CPU power management.
