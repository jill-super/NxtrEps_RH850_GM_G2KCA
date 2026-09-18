---
title: "CSIH 2 Configuration And Use (CM630A_CSIH2CfgAndUse_Design)"
description: "CSIH 2 Configuration And Use (CSIH2CfgAndUse) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

CSIH 2 Configuration And Use (CSIH2CfgAndUse) for the Electric Power Steering controller. 
This is the **functional design** folder for CSIH 2 Configuration And Use (CSIH2CfgAndUse); the compilable sources live in the sibling implementation folder (sibling implementation folder, if present).

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
- [CM630A_CSIH2CfgAndUse.doc](./CM630A-CSIH2CfgAndUse/) — Design / Integration Document
- [AUTOSAR_SWS_SPIHandlerDriver.pdf](./AUTOSAR-SWS-SPIHandlerDriver/) — Portable Document (vendor or generated report)

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `CSIH2CfgAndUse` (code `CM630A`) is retained for traceability; prose on this page uses the expanded long name.
