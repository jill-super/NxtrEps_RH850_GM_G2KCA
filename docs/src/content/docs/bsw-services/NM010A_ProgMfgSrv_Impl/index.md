---
title: "Programming Manufacturing Service (NM010A_ProgMfgSrv_Impl)"
description: "Common Manufacturing Services"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Common Manufacturing Services. 
This is the **implementation** folder for Programming Manufacturing Service (ProgMfgSrv); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Basic Software Services. Origin: Custom (in-house).*

## Key files

- C sources: **17**, headers: **11** (counts from a repository scan).
- Principal sources: `src/SrvFED1.c`, `src/SrvFED3.c`, `src/SrvFED5.c`, `src/SrvFED7.c`, `src/SrvFEDA.c`, `src/SrvFEDB.c`
- Principal headers: `tools/contract/CmnMfgSrvFct.h`, `tools/contract/CmnMfgSrvTyp.h`, `tools/contract/MfgSrvCfg.h`, `tools/contract/ProgMfgSrv_MemMap.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CmnMfgSrvFct.h`, `tools/contract/CmnMfgSrvTyp.h`, `tools/contract/MfgSrvCfg.h`, `tools/contract/Rte.h`, `tools/contract/Rte_Compiler_Cfg.h`, `tools/contract/Rte_MemMap.h`
- Main source: `SrvFED1.c`. No dedicated hand-written interface header; callers use the Runtime Environment contracts listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `ProgMfgSrv` (code `NM010A`) is retained for traceability; prose on this page uses the expanded long name.
