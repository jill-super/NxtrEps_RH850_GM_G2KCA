---
title: "Current Measurement (ES200A_CurrMeas_Impl)"
description: "Implementation of Offset and Gain for CurrMeas"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Offset and Gain for CurrMeas. 
This is the **implementation** folder for Current Measurement (CurrMeas); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES200A_CurrMeas_Design](../ES200A_CurrMeas_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **13** (counts from a repository scan).
- Principal sources: `src/CDD_CurrMeas.c`, `src/CDD_CurrMeas_MotCtrl.c`
- Principal headers: `include/CDD_CurrMeas.h`, `include/CDD_CurrMeas_MotCtrl_MemMap.h`, `tools/contract/CDD_CurrMeas_MemMap.h`, `tools/contract/ElecGlbPrm.h`, `tools/contract/FltInj.h`, `tools/contract/Rte.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_CurrMeas_MemMap.h`, `tools/contract/ElecGlbPrm.h`, `tools/contract/FltInj.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_CurrMeas.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_CurrMeas.h`; main source: `CDD_CurrMeas.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [CurrMeas_IntegrationManual.docx](./CurrMeas-IntegrationManual/) — Integration Manual
- [CurrMeas_MDD.doc](./CurrMeas-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES200A_CurrMeas_Impl/doc/CurrMeas_Review.xlsm`
- `ES200A_CurrMeas_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES200A_CurrMeas_Design](../ES200A_CurrMeas_Design/) and the sources themselves.
- Short name `CurrMeas` (code `ES200A`) is retained for traceability; prose on this page uses the expanded long name.
