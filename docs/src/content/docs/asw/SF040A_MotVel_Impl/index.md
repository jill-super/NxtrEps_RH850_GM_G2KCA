---
title: "Motor Velocity (SF040A_MotVel_Impl)"
description: "Implementation of calculation of Motor Velocity"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of calculation of Motor Velocity. 
This is the **implementation** folder for Motor Velocity (MotVel); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [SF040A_MotVel_Design](../SF040A_MotVel_Design/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **13** (counts from a repository scan).
- Principal sources: `src/CDD_MotVel.c`, `src/CDD_MotVel_MotCtrl.c`
- Principal headers: `include/CDD_MotVel.h`, `include/CDD_MotVel_MotCtrl_MemMap.h`, `include/CDD_MotVel_private.h`, `tools/contract/CDD_MotVel_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_MotVel.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/CDD_MotVel_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_MotVel.h`, `tools/contract/Rte_CDD_MotVel_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_MotVel.h`; main source: `CDD_MotVel.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [MotVel_Integration Manual.docx](./MotVel-Integration-Manual/) — Integration Manual
- [MotVel_MDD.docx](./MotVel-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `SF040A_MotVel_Impl/doc/MotVel_Peer Review Checklists.xlsm`
- `SF040A_MotVel_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF040A_MotVel_Design](../SF040A_MotVel_Design/) and the sources themselves.
- Short name `MotVel` (code `SF040A`) is retained for traceability; prose on this page uses the expanded long name.
