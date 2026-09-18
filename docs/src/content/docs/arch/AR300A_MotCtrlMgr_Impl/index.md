---
title: "Motor Control Manager (AR300A_MotCtrlMgr_Impl)"
description: "Motor Control Manager Interrupt header"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Motor Control Manager Interrupt header. 
This is the **implementation** folder for Motor Control Manager (MotCtrlMgr); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [AR300A_MotCtrlMgr_Design](../AR300A_MotCtrlMgr_Design/).

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **3**, headers: **12** (counts from a repository scan).
- Principal headers: `include/CDD_MotCtrlMgr_Irq.h`, `include/MotCtrlMgr_MemMap.h`, `tools/contract/generate/CDD_MotCtrlMgr_Data.h`, `tools/contract/generate/RteGen/CDD_MotCtrlMgr_MemMap.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_CDD_MotCtrlMgr.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/generate/CDD_MotCtrlMgr_Data.h`, `tools/contract/generate/RteGen/CDD_MotCtrlMgr_MemMap.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_CDD_MotCtrlMgr.h`, `tools/contract/generate/RteGen/Rte_CDD_MotCtrlMgr_Type.h`, `tools/contract/generate/RteGen/Rte_Compiler_Cfg.h`
- Main header: `CDD_MotCtrlMgr_Irq.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

3 document(s) beside the code were converted to Markdown pages in this folder:
- [MotCtrlMgr Integration Manual.doc](./MotCtrlMgr-Integration-Manual/) — Integration Manual
- [MotCtrlMgr_MDD.doc](./MotCtrlMgr-MDD/) — Design / Integration Document
- [MotCtrlMgr DataDictionary Tool User Guide.docx](./MotCtrlMgr-DataDictionary-Tool-User-Guide/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `AR300A_MotCtrlMgr_Impl/doc/MotCtrlMgr Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [AR300A_MotCtrlMgr_Design](../AR300A_MotCtrlMgr_Design/) and the sources themselves.
- Short name `MotCtrlMgr` (code `AR300A`) is retained for traceability; prose on this page uses the expanded long name.
