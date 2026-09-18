---
title: "Non-Volatile M (ES006A_NvM_Impl)"
description: "Implementation of NvM Proxy ES006A"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of NvM Proxy ES006A. 
This is the **implementation** folder for Non-Volatile M (NvM); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES006A_NvM_Design](../ES006A_NvM_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **5**, headers: **19** (counts from a repository scan).
- Principal sources: `src/CDD_NvMProxy.c`, `src/CDD_NvMProxyApi.c`, `src/CDD_NvMProxyNonRte.c`
- Principal headers: `include/CDD_NvMProxy.h`, `tools/contract/CDD_NvMProxy_Cbk.h`, `tools/contract/CDD_NvMProxy_MemMap.h`, `tools/contract/NvM.h`, `tools/contract/NvM_Types.h`, `tools/contract/Rte.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_NvMProxy_MemMap.h`, `tools/contract/NvM.h`, `tools/contract/NvM_Types.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_NvMProxy.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_NvMProxy.h`; main source: `CDD_NvMProxy.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Non-volatile memory handling for calibration data
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [ES006A_NvM_Integration_Manual.doc](./ES006A-NvM-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `ES006A_NvM_Impl/doc/NvMProxy Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES006A_NvM_Design](../ES006A_NvM_Design/) and the sources themselves.
- Short name `NvM` (code `ES006A`) is retained for traceability; prose on this page uses the expanded long name.
