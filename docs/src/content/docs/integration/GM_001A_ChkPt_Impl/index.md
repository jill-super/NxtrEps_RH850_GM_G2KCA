---
title: "Checkpoint Handling (GM_001A_ChkPt_Impl)"
description: "Implementation of GM Checkpoint Component (RTE)"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of GM Checkpoint Component (RTE). 
This is the **implementation** folder for Checkpoint Handling (001A_ChkPt); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: System Integration and Platform. Origin: Custom (in-house).*

## Key files

- C sources: **3**, headers: **20** (counts from a repository scan).
- Principal sources: `src/CDD_ChkPtAppl10.c`, `src/CDD_ChkPtAppl6.c`, `src/CDD_ChkPt_Bsw.c`
- Principal headers: `include/CDD_ChkPt_Bsw.h`, `tools/contract/CDD_ChkPtAppl6/CDD_ChkPtAppl6_MemMap.h`, `tools/contract/CDD_ChkPtAppl6/Rte.h`, `tools/contract/CDD_ChkPtAppl6/Rte_CDD_ChkPtAppl6.h`, `tools/contract/CDD_ChkPtAppl6/Rte_Compiler_Cfg.h`, `tools/contract/CDD_ChkPtAppl6/Rte_MemMap.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_ChkPtAppl6/CDD_ChkPtAppl6_MemMap.h`, `tools/contract/CDD_ChkPtAppl6/Rte.h`, `tools/contract/CDD_ChkPtAppl6/Rte_CDD_ChkPtAppl6.h`, `tools/contract/CDD_ChkPtAppl6/Rte_Compiler_Cfg.h`, `tools/contract/CDD_ChkPtAppl6/Rte_Type.h`, `tools/contract/Os.h`
- Main header: `CDD_ChkPt_Bsw.h`; main source: `CDD_ChkPtAppl10.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [ChkPt Integration Manual.doc](./ChkPt-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `GM_001A_ChkPt_Impl/doc/ChkPt Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `001A_ChkPt` (code `GM`) is retained for traceability; prose on this page uses the expanded long name.
