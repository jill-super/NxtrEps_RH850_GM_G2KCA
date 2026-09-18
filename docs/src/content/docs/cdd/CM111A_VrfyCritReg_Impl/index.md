---
title: "Verify Critical Registers (CM111A_VrfyCritReg_Impl)"
description: "Implementation of Critical Register Verification FDD CM111A"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Implementation of Critical Register Verification FDD CM111A. 
This is the **implementation** folder for Verify Critical Registers (VrfyCritReg); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [CM111A_VrfyCritReg_Design](../CM111A_VrfyCritReg_Design/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **11** (counts from a repository scan).
- Principal sources: `src/CDD_VrfyCritReg.c`
- Principal headers: `include/CDD_VrfyCritReg.h`, `tools/contract/generate/CDD_VrfyCritReg_Cfg_private.h`, `tools/contract/generate/Os.h`, `tools/contract/generate/RteGen/CDD_VrfyCritReg_MemMap.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_CDD_VrfyCritReg.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/generate/CDD_VrfyCritReg_Cfg_private.h`, `tools/contract/generate/Os.h`, `tools/contract/generate/RteGen/CDD_VrfyCritReg_MemMap.h`, `tools/contract/generate/RteGen/Rte.h`, `tools/contract/generate/RteGen/Rte_CDD_VrfyCritReg.h`, `tools/contract/generate/RteGen/Rte_CDD_VrfyCritReg_Type.h`
- Main header: `CDD_VrfyCritReg.h`; main source: `CDD_VrfyCritReg.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [VrfyCritReg_IntegrationManual.doc](./VrfyCritReg-IntegrationManual/) — Integration Manual
- [VrfyCritReg_MDD.docx](./VrfyCritReg-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM111A_VrfyCritReg_Impl/doc/VrfyCritReg_Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM111A_VrfyCritReg_Design](../CM111A_VrfyCritReg_Design/) and the sources themselves.
- Short name `VrfyCritReg` (code `CM111A`) is retained for traceability; prose on this page uses the expanded long name.
