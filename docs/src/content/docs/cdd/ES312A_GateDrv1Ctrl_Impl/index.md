---
title: "Gate Driver 1 Control (ES312A_GateDrv1Ctrl_Impl)"
description: "Gate Drive 1 Control function responsible for configuration, deactivation and determination of fault status for Gate Drive 1"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Gate Drive 1 Control function responsible for configuration, deactivation and determination of fault status for Gate Drive 1. 
This is the **implementation** folder for Gate Driver 1 Control (GateDrv1Ctrl); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES312A_GateDrv1Ctrl_Design](../ES312A_GateDrv1Ctrl_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **12** (counts from a repository scan).
- Principal sources: `src/GateDrv1Ctrl.c`
- Principal headers: `tools/contract/ElecGlbPrm.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_DataHandleType.h`, `tools/contract/Rte_GateDrv1Ctrl_Type.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/ElecGlbPrm.h`, `tools/contract/Os.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_GateDrv1Ctrl_Type.h`, `tools/contract/Rte_MemMap.h`
- Main source: `GateDrv1Ctrl.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [GateDrv1Ctrl_IntegrationManual.doc](./GateDrv1Ctrl-IntegrationManual/) — Integration Manual
- [GateDrv1Ctrl_MDD.doc](./GateDrv1Ctrl-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES312A_GateDrv1Ctrl_Impl/doc/GateDrv1Ctrl_PeerReviewChecklist.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES312A_GateDrv1Ctrl_Design](../ES312A_GateDrv1Ctrl_Design/) and the sources themselves.
- Short name `GateDrv1Ctrl` (code `ES312A`) is retained for traceability; prose on this page uses the expanded long name.
