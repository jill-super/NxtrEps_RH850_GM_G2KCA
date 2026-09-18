---
title: "Diagnostic Manager (ES101A_DiagcMgr_Impl)"
description: "Implementation of Diagnostic Manager FDD ES101A"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Diagnostic Manager FDD ES101A. 
This is the **implementation** folder for Diagnostic Manager (DiagcMgr); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES101A_DiagcMgr_Design](../ES101A_DiagcMgr_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **17**, headers: **140** (counts from a repository scan).
- Principal sources: `src/DiagcMgrNonRTE.c`, `src/DiagcMgrProxyAppl0.c`, `src/DiagcMgrProxyAppl1.c`, `src/DiagcMgrProxyAppl3.c`, `src/DiagcMgrProxyAppl4.c`, `src/DiagcMgrProxyAppl6.c`
- Principal headers: `include/DiagcMgr.h`, `include/DiagcMgrStaticTypes.h`, `include/DiagcMgr_private.h`, `tools/contract/generate/DiagcMgr_Cfg.h`, `tools/contract/generate/RteGen/CDD_NvMProxy.h`, `tools/contract/generate/RteGen/Dem.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/generate/DiagcMgr_Cfg.h`, `tools/contract/generate/RteGen/CDD_NvMProxy.h`, `tools/contract/generate/RteGen/Dem.h`, `tools/contract/generate/RteGen/Dem_Cdd_Types.h`, `tools/contract/generate/RteGen/Dem_Lcfg.h`, `tools/contract/generate/RteGen/Dem_Types.h`
- Main header: `DiagcMgr.h`; main source: `DiagcMgrNonRTE.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

3 document(s) beside the code were converted to Markdown pages in this folder:
- [DiagcMgrProxy_MDD.doc](./DiagcMgrProxy-MDD/) — Design / Integration Document
- [DiagcMgr_IntegrationManual.doc](./DiagcMgr-IntegrationManual/) — Integration Manual
- [DiagcMgr_MDD.doc](./DiagcMgr-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES101A_DiagcMgr_Impl/doc/DiagcMgr Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES101A_DiagcMgr_Design](../ES101A_DiagcMgr_Design/) and the sources themselves.
- Short name `DiagcMgr` (code `ES101A`) is retained for traceability; prose on this page uses the expanded long name.
