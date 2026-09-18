---
title: "Motor Current Regulator Voltage Limiter (SF105A_MotCurrRegVltgLimr_Impl)"
description: "Implementation of Motor Current Regulator and Voltage limiter"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Motor Current Regulator and Voltage limiter. 
This is the **implementation** folder for Motor Current Regulator Voltage Limiter (MotCurrRegVltgLimr); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [SF105A_MotCurrRegVltgLimr_Design](../SF105A_MotCurrRegVltgLimr_Design/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **14** (counts from a repository scan).
- Principal sources: `src/CDD_MotCurrRegVltgLimr.c`, `src/CDD_MotCurrRegVltgLimr_MotCtrl.c`
- Principal headers: `include/CDD_MotCurrRegVltgLimr.h`, `include/CDD_MotCurrRegVltgLimr_MotCtrl_MemMap.h`, `tools/contract/CDD_MotCurrRegVltgLimr_MemMap.h`, `tools/contract/ElecGlbPrm.h`, `tools/contract/MotRefMdl.h`, `tools/contract/Rte.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_MotCurrRegVltgLimr_MemMap.h`, `tools/contract/ElecGlbPrm.h`, `tools/contract/MotRefMdl.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_MotCurrRegVltgLimr_Type.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_MotCurrRegVltgLimr.h`; main source: `CDD_MotCurrRegVltgLimr.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [MotCurrRegVltgLimr_Integration Manual.docx](./MotCurrRegVltgLimr-Integration-Manual/) — Integration Manual
- [MotCurrRegVltgLimr_MDD.docx](./MotCurrRegVltgLimr-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `SF105A_MotCurrRegVltgLimr_Impl/doc/MotCurrRegVltgLimr_Peer Review Checklists.xlsm`
- `SF105A_MotCurrRegVltgLimr_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF105A_MotCurrRegVltgLimr_Design](../SF105A_MotCurrRegVltgLimr_Design/) and the sources themselves.
- Short name `MotCurrRegVltgLimr` (code `SF105A`) is retained for traceability; prose on this page uses the expanded long name.
