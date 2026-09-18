---
title: "Analog to Digital Converter 0 Configuration And Use (CM300A_Adc0CfgAndUse_Impl)"
description: "Nexteer ADC0 Initialisation"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Nexteer ADC0 Initialisation. 
This is the **implementation** folder for Analog to Digital Converter 0 Configuration And Use (Adc0CfgAndUse); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **2**, headers: **12** (counts from a repository scan).
- Principal sources: `src/CDD_Adc0CfgAndUse.c`, `src/CDD_Adc0CfgAndUse_MotCtrl.c`
- Principal headers: `include/CDD_Adc0CfgAndUse.h`, `include/CDD_Adc0CfgAndUse_MotCtrl_MemMap.h`, `tools/contract/CDD_Adc0CfgAndUse_Cfg.h`, `tools/contract/CDD_Adc0CfgAndUse_MemMap.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/Rte.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_Adc0CfgAndUse_Cfg.h`, `tools/contract/CDD_Adc0CfgAndUse_MemMap.h`, `tools/contract/CDD_MotCtrlMgr_Data.h`, `tools/contract/Rte.h`, `tools/contract/Rte_CDD_Adc0CfgAndUse.h`, `tools/contract/Rte_Compiler_Cfg.h`
- Main header: `CDD_Adc0CfgAndUse.h`; main source: `CDD_Adc0CfgAndUse.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [Adc0CfgAndUse_IntegrationManual.docx](./Adc0CfgAndUse-IntegrationManual/) — Integration Manual
- [Adc0CfgAndUse_MDD.doc](./Adc0CfgAndUse-MDD/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `CM300A_Adc0CfgAndUse_Impl/doc/Adc0CfgAndUse_Review.xlsm`
- `CM300A_Adc0CfgAndUse_Impl/doc/requirements.csv`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Adc0CfgAndUse` (code `CM300A`) is retained for traceability; prose on this page uses the expanded long name.
