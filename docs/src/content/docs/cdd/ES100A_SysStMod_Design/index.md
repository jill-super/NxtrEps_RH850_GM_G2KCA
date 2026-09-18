---
title: "System State Mode (ES100A_SysStMod_Design)"
description: "System State Mode (SysStMod) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

System State Mode (SysStMod) for the Electric Power Steering controller. 
This is the **functional design** folder for System State Mode (SysStMod); the compilable sources live in the sibling implementation folder [ES100A_SysStMod_Impl](../ES100A_SysStMod_Impl/).

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **0** (counts from a repository scan).
- Also present: design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Interface is delivered through the Runtime Environment contracts and configuration listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [ES100A_SysStMod.doc](./ES100A-SysStMod/) — Design / Integration Document
- [ES100A_SysStMod_DDReport.txt](./ES100A-SysStMod-DDReport/) — Design Document / Report

Related artefacts kept in their native format (not converted):
- `ES100A_SysStMod_Design/Doc/ES100A_SysStMod FDD Peer Review Checklist.xlsx`
- `ES100A_SysStMod_Design/Doc/VectorAnalysis.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES100A_SysStMod_Impl](../ES100A_SysStMod_Impl/) and the sources themselves.
- Short name `SysStMod` (code `ES100A`) is retained for traceability; prose on this page uses the expanded long name.
