---
title: "State Health Signal Static (ES106A_StHlthSigStc_Impl)"
description: "Implementation of State of Health Signal Statistics"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of State of Health Signal Statistics. 
This is the **implementation** folder for State Health Signal Static (StHlthSigStc); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [ES106A_StHlthSigStc_Design](../ES106A_StHlthSigStc_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **15** (counts from a repository scan).
- Principal sources: `src/StHlthSigStc.c`
- Principal headers: `include/StHlthSigStc.h`, `tools/contract/generate/RteGen/Crc.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_Compiler_Cfg.h`, `tools/contract/generate/RteGen/Rte_MemMap.h`, `tools/contract/generate/RteGen/Rte_StHlthSigStc.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/generate/RteGen/Crc.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_Compiler_Cfg.h`, `tools/contract/generate/RteGen/Rte_StHlthSigStc.h`, `tools/contract/generate/RteGen/Rte_StHlthSigStc_Type.h`, `tools/contract/generate/RteGen/Rte_Type.h`
- Main header: `StHlthSigStc.h`; main source: `StHlthSigStc.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [StHlthSigStc_IntegrationManual.doc](./StHlthSigStc-IntegrationManual/) — Integration Manual
- [StHlthSigStc_MDD.doc](./StHlthSigStc-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `ES106A_StHlthSigStc_Impl/doc/StHlthSigStc Review.xlsm`
- `ES106A_StHlthSigStc_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES106A_StHlthSigStc_Design](../ES106A_StHlthSigStc_Design/) and the sources themselves.
- Short name `StHlthSigStc` (code `ES106A`) is retained for traceability; prose on this page uses the expanded long name.
