---
title: "Internal Motor Control Arbitration (AR350A_ImcArbn_Impl)"
description: "Implementation of Inter-Micro Communication Arbitration"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Inter-Micro Communication Arbitration. 
This is the **implementation** folder for Internal Motor Control Arbitration (ImcArbn); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [AR350A_ImcArbn_Design](../AR350A_ImcArbn_Design/).

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **14** (counts from a repository scan).
- Principal sources: `src/ImcArbn.c`
- Principal headers: `include/ImcArbn.h`, `tools/contract/Crc.h`, `tools/contract/NxtrDet.h`, `tools/contract/generate/ImcArbn_Cfg.h`, `tools/contract/generate/ImcArbn_Private_Cfg.h`, `tools/contract/generate/RteGen/ImcArbn_MemMap.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/Crc.h`, `tools/contract/NxtrDet.h`, `tools/contract/generate/ImcArbn_Cfg.h`, `tools/contract/generate/ImcArbn_Private_Cfg.h`, `tools/contract/generate/RteGen/ImcArbn_MemMap.h`, `tools/contract/generate/RteGen/Rte_Compiler_Cfg.h`
- Main header: `ImcArbn.h`; main source: `ImcArbn.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [ImcArbn_IntegrationManual.doc](./ImcArbn-IntegrationManual/) — Integration Manual
- [ImcArbn_MDD.doc](./ImcArbn-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `AR350A_ImcArbn_Impl/doc/ImcArbn_Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [AR350A_ImcArbn_Design](../AR350A_ImcArbn_Design/) and the sources themselves.
- Short name `ImcArbn` (code `AR350A`) is retained for traceability; prose on this page uses the expanded long name.
