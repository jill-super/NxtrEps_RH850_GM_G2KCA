---
title: "Electronic Control Module Output and Diagnostic (CM104A_EcmOutpAndDiagc_Impl)"
description: "Error Control Module Output and Diagnostics Complex Driver"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Error Control Module Output and Diagnostics Complex Driver. 
This is the **implementation** folder for Electronic Control Module Output and Diagnostic (EcmOutpAndDiagc); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [CM104A_EcmOutpAndDiagc_Design](../CM104A_EcmOutpAndDiagc_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **11** (counts from a repository scan).
- Principal sources: `src/CDD_EcmOutpAndDiagc.c`, `src/CDD_EcmOutpAndDiagcNonRte.c`
- Principal headers: `include/CDD_EcmOutpAndDiagc.h`, `tools/contract/CDD_EcmOutpAndDiagc_MemMap.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_EcmOutpAndDiagc.h`, `tools/contract/Rte_CDD_EcmOutpAndDiagc_Type.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_EcmOutpAndDiagc_MemMap.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_EcmOutpAndDiagc.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_MemMap.h`
- Main header: `CDD_EcmOutpAndDiagc.h`; main source: `CDD_EcmOutpAndDiagc.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [EcmOutpAndDiagc Integration Manual.doc](./EcmOutpAndDiagc-Integration-Manual/) — Integration Manual
- [EcmOutpAndDiagc Module Design Document.docx](./EcmOutpAndDiagc-Module-Design-Document/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM104A_EcmOutpAndDiagc_Impl/doc/EcmOutpAndDiagc Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM104A_EcmOutpAndDiagc_Design](../CM104A_EcmOutpAndDiagc_Design/) and the sources themselves.
- Short name `EcmOutpAndDiagc` (code `CM104A`) is retained for traceability; prose on this page uses the expanded long name.
