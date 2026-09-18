---
title: "Motor Ag0 Measurement (CM620C_MotAg0Meas_Impl)"
description: "Implementation of Motor Angle 0 Measurement component"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Motor Angle 0 Measurement component. 
This is the **implementation** folder for Motor Ag0 Measurement (MotAg0Meas); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [CM620C_MotAg0Meas_Design](../CM620C_MotAg0Meas_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **15** (counts from a repository scan).
- Principal sources: `src/CDD_MotAg0Meas.c`, `src/CDD_MotAg0Meas_MotCtrl.c`
- Principal headers: `include/CDD_MotAg0Meas.h`, `include/CDD_MotAg0Meas_MotCtrl_MemMap.h`, `include/CDD_MotAg0Meas_private.h`, `tools/contract/CDD_MotAg3Meas.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/FltInj.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_MotAg3Meas.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/FltInj.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`
- Main header: `CDD_MotAg0Meas.h`; main source: `CDD_MotAg0Meas.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [MotAg0Meas_IntegrationManual.doc](./MotAg0Meas-IntegrationManual/) — Integration Manual
- [MotAg0Meas_MDD.doc](./MotAg0Meas-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM620C_MotAg0Meas_Impl/doc/MotAg0Meas_PeerReviewChecklist.xlsx`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM620C_MotAg0Meas_Design](../CM620C_MotAg0Meas_Design/) and the sources themselves.
- Short name `MotAg0Meas` (code `CM620C`) is retained for traceability; prose on this page uses the expanded long name.
