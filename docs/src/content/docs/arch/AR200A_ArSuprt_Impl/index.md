---
title: "AUTOSAR Support (AR200A_ArSuprt_Impl)"
description: "This file contains a stub header for component unit test and static analysis usage"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

This file contains a stub header for component unit test and static analysis usage. 
This is the **implementation** folder for AUTOSAR Support (ArSuprt); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **6** (counts from a repository scan).
- Principal headers: `include/ASR4.0.3/ComStack_Types.h`, `include/ASR4.0.3/Std_Types.h`, `tools/contract/Det.h`, `tools/contract/Mcu.h`, `tools/contract/MemMap.h`, `tools/contract/Os.h`
- Also present: `tools/` Green Hills project files and generation contracts.

## Public interface and usage

- Runtime Environment contracts: `tools/contract/Det.h`, `tools/contract/Mcu.h`, `tools/contract/MemMap.h`, `tools/contract/Os.h`
- Main header: `ComStack_Types.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `ArSuprt` (code `AR200A`) is retained for traceability; prose on this page uses the expanded long name.
