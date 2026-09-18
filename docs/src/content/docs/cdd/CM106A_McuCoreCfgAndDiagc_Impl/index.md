---
title: "Microcontroller Core Configuration and Diagnostic (CM106A_McuCoreCfgAndDiagc_Impl)"
description: "Microcontroller Unit Core Configuration and Diagnostics Complex Driver"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Microcontroller Unit Core Configuration and Diagnostics Complex Driver. 
This is the **implementation** folder for Microcontroller Core Configuration and Diagnostic (McuCoreCfgAndDiagc); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [CM106A_McuCoreCfgAndDiagc_Design](../CM106A_McuCoreCfgAndDiagc_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **9** (counts from a repository scan).
- Principal sources: `src/CDD_McuCoreCfgAndDiagc.c`, `src/CDD_McuCoreCfgAndDiagcNonRte.c`
- Principal headers: `include/CDD_McuCoreCfgAndDiagc.h`, `tools/contract/CDD_McuCoreCfgAndDiagc_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_McuCoreCfgAndDiagc.h`, `tools/contract/Rte_CDD_McuCoreCfgAndDiagc_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_McuCoreCfgAndDiagc_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_McuCoreCfgAndDiagc.h`, `tools/contract/Rte_CDD_McuCoreCfgAndDiagc_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`
- Main header: `CDD_McuCoreCfgAndDiagc.h`; main source: `CDD_McuCoreCfgAndDiagc.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [McuCoreCfgAndDiagc Integration Manual.doc](./McuCoreCfgAndDiagc-Integration-Manual/) — Integration Manual
- [McuCoreCfgAndDiagc Module Design Document.docx](./McuCoreCfgAndDiagc-Module-Design-Document/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM106A_McuCoreCfgAndDiagc_Impl/doc/McuCoreCfgAndDiagc Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM106A_McuCoreCfgAndDiagc_Design](../CM106A_McuCoreCfgAndDiagc_Design/) and the sources themselves.
- Short name `McuCoreCfgAndDiagc` (code `CM106A`) is retained for traceability; prose on this page uses the expanded long name.
