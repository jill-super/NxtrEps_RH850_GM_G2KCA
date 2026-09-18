---
title: "Handwheel Torque Arbitration (ES228A_HwTqArbn_Impl)"
description: "Arbitration between multiple Torque sensors and calculation of handwheel torque"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Arbitration between multiple Torque sensors and calculation of handwheel torque. 
This is the **implementation** folder for Handwheel Torque Arbitration (HwTqArbn); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES228A_HwTqArbn_Design](../ES228A_HwTqArbn_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **8** (counts from a repository scan).
- Principal sources: `src/HwTqArbn.c`
- Principal headers: `tools/contract/HwTqArbn_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_HwTqArbn.h`, `tools/contract/Rte_HwTqArbn_Type.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/HwTqArbn_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_HwTqArbn.h`, `tools/contract/Rte_HwTqArbn_Type.h`
- Main source: `HwTqArbn.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [HwTqArbn_IntegrationManual.doc](./HwTqArbn-IntegrationManual/) — Integration Manual
- [HwTqArbn_MDD.doc](./HwTqArbn-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES228A_HwTqArbn_Impl/doc/HwTqArbn_PeerReviewChecklist.xlsm`
- `ES228A_HwTqArbn_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES228A_HwTqArbn_Design](../ES228A_HwTqArbn_Design/) and the sources themselves.
- Short name `HwTqArbn` (code `ES228A`) is retained for traceability; prose on this page uses the expanded long name.
