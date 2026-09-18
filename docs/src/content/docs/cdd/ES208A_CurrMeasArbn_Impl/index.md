---
title: "Current Measurement Arbitration (ES208A_CurrMeasArbn_Impl)"
description: "Implementation of Arbitration of Current Measurement signals"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Arbitration of Current Measurement signals. 
This is the **implementation** folder for Current Measurement Arbitration (CurrMeasArbn); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES208A_CurrMeasArbn_Design](../ES208A_CurrMeasArbn_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **11** (counts from a repository scan).
- Principal sources: `src/CDD_CurrMeasArbn.c`, `src/CDD_CurrMeasArbn_MotCtrl.c`
- Principal headers: `include/CDD_CurrMeasArbn.h`, `include/CDD_CurrMeasArbn_MotCtrl_MemMap.h`, `tools/contract/CDD_CurrMeasArbn_MemMap.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_CurrMeasArbn.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_CurrMeasArbn_MemMap.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_CurrMeasArbn.h`, `tools/contract/Rte_CDD_CurrMeasArbn_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_CurrMeasArbn.h`; main source: `CDD_CurrMeasArbn.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [CurrMeasArbn_IntegrationManual.docx](./CurrMeasArbn-IntegrationManual/) — Integration Manual
- [CurrMeasArbn_MDD.doc](./CurrMeasArbn-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES208A_CurrMeasArbn_Impl/doc/CurrMeasArbn_ Review.xlsm`
- `ES208A_CurrMeasArbn_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES208A_CurrMeasArbn_Design](../ES208A_CurrMeasArbn_Design/) and the sources themselves.
- Short name `CurrMeasArbn` (code `ES208A`) is retained for traceability; prose on this page uses the expanded long name.
