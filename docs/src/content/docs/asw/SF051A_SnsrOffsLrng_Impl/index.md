---
title: "Sensor Offset Learning (SF051A_SnsrOffsLrng_Impl)"
description: "Sensor Offset learning"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Sensor Offset learning. 
This is the **implementation** folder for Sensor Offset Learning (SnsrOffsLrng); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [SF051A_SnsrOffsLrng_Design](../SF051A_SnsrOffsLrng_Design/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **9** (counts from a repository scan).
- Principal sources: `src/SnsrOffsLrng.c`
- Principal headers: `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_MemMap.h`, `tools/contract/Rte_SnsrOffsLrng.h`, `tools/contract/Rte_SnsrOffsLrng_Type.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_MemMap.h`, `tools/contract/Rte_SnsrOffsLrng_Type.h`, `tools/contract/Rte_Type.h`
- Main source: `SnsrOffsLrng.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [SnsrOffLrng_MDD.docx](./SnsrOffLrng-MDD/) — Design / Integration Document
- [SnsrOffsLrng_IntegrationManual.doc](./SnsrOffsLrng-IntegrationManual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `SF051A_SnsrOffsLrng_Impl/doc/SnsrOffLrng_ReviewChecklists.xlsm`
- `SF051A_SnsrOffsLrng_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF051A_SnsrOffsLrng_Design](../SF051A_SnsrOffsLrng_Design/) and the sources themselves.
- Short name `SnsrOffsLrng` (code `SF051A`) is retained for traceability; prose on this page uses the expanded long name.
