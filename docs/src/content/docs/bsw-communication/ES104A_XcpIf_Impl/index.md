---
title: "Universal Measurement and Calibration Protocol Interface (ES104A_XcpIf_Impl)"
description: "Source file for XCP Interface ES 104A"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Source file for XCP Interface ES 104A. 
This is the **implementation** folder for Universal Measurement and Calibration Protocol Interface (XcpIf); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Basic Software Communication Stack. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **13** (counts from a repository scan).
- Principal sources: `src/CDD_XcpIf.c`
- Principal headers: `include/CDD_XcpIf.h`, `include/CDD_XcpIf_private.h`, `tools/contract/CDD_NxtrTi.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_XcpIf.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_NxtrTi.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_XcpIf.h`, `tools/contract/Rte_CDD_XcpIf_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_XcpIf.h`; main source: `CDD_XcpIf.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [XcpIf Integration Manual.docx](./XcpIf-Integration-Manual/) — Integration Manual
- [XcpIf_MDD.docx](./XcpIf-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES104A_XcpIf_Impl/doc/XcpIf Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `XcpIf` (code `ES104A`) is retained for traceability; prose on this page uses the expanded long name.
