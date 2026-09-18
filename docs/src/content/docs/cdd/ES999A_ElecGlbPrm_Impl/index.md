---
title: "Electrical Global Parameters (ES999A_ElecGlbPrm_Impl)"
description: "Electrical global parameter definitions"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Electrical global parameter definitions. 
This is the **implementation** folder for Electrical Global Parameters (ElecGlbPrm); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES999A_ElecGlbPrm_Design](../ES999A_ElecGlbPrm_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **3**, headers: **4** (counts from a repository scan).
- Principal sources: `src/ElecGlbPrm.c`, `tools/local/src/ElecGlbPrm_StaticAnalysisStub.c`
- Principal headers: `include/ElecGlbPrm.h`, `include/ElecGlbPrm_MemMap.h`, `tools/local/generate/ElecGlbPrm_Cfg.h`, `tools/local/generate/Rte_Stubs.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/local/generate/Rte_Stubs.h`
- Main header: `ElecGlbPrm.h`; main source: `ElecGlbPrm.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [ElecGlbPrm_IntegrationManual.doc](./ElecGlbPrm-IntegrationManual/) — Integration Manual
- [DRS.txt](./DRS/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `ES999A_ElecGlbPrm_Impl/doc/ElecGlbPrm Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES999A_ElecGlbPrm_Design](../ES999A_ElecGlbPrm_Design/) and the sources themselves.
- Short name `ElecGlbPrm` (code `ES999A`) is retained for traceability; prose on this page uses the expanded long name.
