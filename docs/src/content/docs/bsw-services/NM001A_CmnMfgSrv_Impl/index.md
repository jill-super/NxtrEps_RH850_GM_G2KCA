---
title: "Common Manufacturing Service (NM001A_CmnMfgSrv_Impl)"
description: "Common Manufacturing Services Main Functions"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Common Manufacturing Services Main Functions. 
This is the **implementation** folder for Common Manufacturing Service (CmnMfgSrv); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Basic Software Services. Origin: Custom (in-house).*

## Key files

- C sources: **133**, headers: **21** (counts from a repository scan).
- Principal sources: `src/SrvFD3C.c`, `src/SrvFD70.c`, `src/SrvFDA8.c`, `src/SrvFDB0.c`, `src/SrvFDB1.c`, `src/SrvFDB8.c`
- Principal headers: `include/CmnMfgSrv.h`, `include/CmnMfgSrvFct.h`, `include/CmnMfgSrvTyp.h`, `include/CmnMfgSrv_NxtrMemMap.h`, `tools/contract/CmnMfgSrv_MemMap.h`, `tools/contract/Crc.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CmnMfgSrv_MemMap.h`, `tools/contract/Crc.h`, `tools/contract/Det.h`, `tools/contract/FltInj.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CmnMfgSrv.h`; main source: `SrvFD3C.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

4 document(s) beside the code were converted to Markdown pages in this folder:
- [Development.txt](./Development/) — Text Note / Report
- [Integration.txt](./Integration/) — Text Note / Report
- [OdxGuide.txt](./OdxGuide/) — Text Note / Report
- [README.txt](./README/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `NM001A_CmnMfgSrv_Impl/doc/CmnMfgSrv_PeerReviewChecklist.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `CmnMfgSrv` (code `NM001A`) is retained for traceability; prose on this page uses the expanded long name.
