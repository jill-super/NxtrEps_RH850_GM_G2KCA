---
title: "Handwheel Tq2 Measurement (CM680A_HwTq2Meas_Design)"
description: "Handwheel Tq2 Measurement (HwTq2Meas) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Handwheel Tq2 Measurement (HwTq2Meas) for the Electric Power Steering controller. 
This is the **functional design** folder for Handwheel Tq2 Measurement (HwTq2Meas); the compilable sources live in the sibling implementation folder [CM680A_HwTq2Meas_Impl](../CM680A_HwTq2Meas_Impl/).

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
- [CM680A_HwTq2Meas_DDReport.txt](./CM680A-HwTq2Meas-DDReport/) — Design Document / Report
- [CM680A_HwTq2Meas_DDReport.txt](./CM680A-HwTq2Meas-DDReport-2/) — Design Document / Report

Related artefacts kept in their native format (not converted):
- `CM680A_HwTq2Meas_Design/Design/CM680A_HwTq2Meas_RSENTPeripheralCfg.xlsx`
- `CM680A_HwTq2Meas_Design/Doc/CM680A_HwTq2Meas_FDD_Checklist.xlsx`
- `CM680A_HwTq2Meas_Design/Reports/CM680A__HwTq2Meas_FuncReq.xlsx`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM680A_HwTq2Meas_Impl](../CM680A_HwTq2Meas_Impl/) and the sources themselves.
- Short name `HwTq2Meas` (code `CM680A`) is retained for traceability; prose on this page uses the expanded long name.
