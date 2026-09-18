---
title: "Assist Summation Limiter (SF004B_AssiSumLim_Impl)"
description: "Implementation of Assist Summation and Limiting FDD SF004B"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Assist Summation and Limiting FDD SF004B. 
This is the **implementation** folder for Assist Summation Limiter (AssiSumLim); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [SF004B_AssiSumLim_Design](../SF004B_AssiSumLim_Design/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **9** (counts from a repository scan).
- Principal sources: `src/AssiSumLim.c`
- Principal headers: `tools/contract/AssiSumLim_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_AssiSumLim.h`, `tools/contract/Rte_AssiSumLim_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/AssiSumLim_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_AssiSumLim.h`, `tools/contract/Rte_AssiSumLim_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_MemMap.h`
- Main source: `AssiSumLim.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AssiSumLim_Integration Manual.docx](./AssiSumLim-Integration-Manual/) — Integration Manual
- [AssiSumLim_MDD.docx](./AssiSumLim-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `SF004B_AssiSumLim_Impl/doc/AssiSumLim_PeerReview.xlsm`
- `SF004B_AssiSumLim_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF004B_AssiSumLim_Design](../SF004B_AssiSumLim_Design/) and the sources themselves.
- Short name `AssiSumLim` (code `SF004B`) is retained for traceability; prose on this page uses the expanded long name.
