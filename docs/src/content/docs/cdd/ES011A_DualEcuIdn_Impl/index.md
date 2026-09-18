---
title: "Dual Electronic Control Unit Identification (ES011A_DualEcuIdn_Impl)"
description: "Implementation of Dual Ecu Identification"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Dual Ecu Identification. 
This is the **implementation** folder for Dual Electronic Control Unit Identification (DualEcuIdn); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES011A_DualEcuIdn_Design](../ES011A_DualEcuIdn_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **9** (counts from a repository scan).
- Principal sources: `src/DualEcuIdn.c`
- Principal headers: `tools/contract/DualEcuIdn_MemMap.h`, `tools/contract/ImcArbn.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_DualEcuIdn.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/ImcArbn.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_DualEcuIdn.h`, `tools/contract/Rte_DualEcuIdn_Type.h`
- Main source: `DualEcuIdn.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [DualEcuIdn_IntegrationManual.docx](./DualEcuIdn-IntegrationManual/) — Integration Manual
- [DualEcuIdn_MDD.doc](./DualEcuIdn-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES011A_DualEcuIdn_Impl/doc/DualEcuIdn_ReviewChecklist.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES011A_DualEcuIdn_Design](../ES011A_DualEcuIdn_Design/) and the sources themselves.
- Short name `DualEcuIdn` (code `ES011A`) is retained for traceability; prose on this page uses the expanded long name.
