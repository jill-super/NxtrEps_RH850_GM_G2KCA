---
title: "Analog to Digital Converter Diagnostic (CM340A_AdcDiagc_Impl)"
description: "Implementation of Adc Diagnostics"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Adc Diagnostics. 
This is the **implementation** folder for Analog to Digital Converter Diagnostic (AdcDiagc); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [CM340A_AdcDiagc_Design](../CM340A_AdcDiagc_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **8** (counts from a repository scan).
- Principal sources: `src/CDD_AdcDiagc.c`
- Principal headers: `tools/contract/CDD_AdcDiagc_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_AdcDiagc.h`, `tools/contract/Rte_CDD_AdcDiagc_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_AdcDiagc_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_AdcDiagc.h`, `tools/contract/Rte_CDD_AdcDiagc_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`
- Main source: `CDD_AdcDiagc.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AdcDiagc_IntegrationManual.doc](./AdcDiagc-IntegrationManual/) — Integration Manual
- [AdcDiagc_MDD.docx](./AdcDiagc-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM340A_AdcDiagc_Impl/doc/AdcDiagc_PeerReviewCheckList.xlsm`
- `CM340A_AdcDiagc_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM340A_AdcDiagc_Design](../CM340A_AdcDiagc_Design/) and the sources themselves.
- Short name `AdcDiagc` (code `CM340A`) is retained for traceability; prose on this page uses the expanded long name.
