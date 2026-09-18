---
title: "Nexteer Software Identifications (NM003A_NxtrSwIds_Impl)"
description: "Nexteer Software Identification"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Nexteer Software Identification. 
This is the **implementation** folder for Nexteer Software Identifications (NxtrSwIds); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Basic Software Services. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **9** (counts from a repository scan).
- Principal sources: `src/NxtrSwIds.c`
- Principal headers: `include/NxtrSwIds.h`, `tools/contract/NxtrSwIds_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_MemMap.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/NxtrSwIds_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_MemMap.h`, `tools/contract/Rte_NxtrSwIds.h`
- Main header: `NxtrSwIds.h`; main source: `NxtrSwIds.c`.
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
- Short name `NxtrSwIds` (code `NM003A`) is retained for traceability; prose on this page uses the expanded long name.
