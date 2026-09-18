---
title: "Direct Memory Access Configuration and Usage (CM200C_DmaCfgAndUse_Design)"
description: "Direct Memory Access Configuration and Usage (DmaCfgAndUse) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Direct Memory Access Configuration and Usage (DmaCfgAndUse) for the Electric Power Steering controller. 
This is the **functional design** folder for Direct Memory Access Configuration and Usage (DmaCfgAndUse); the compilable sources live in the sibling implementation folder [CM200C_DmaCfgAndUse_Impl](../CM200C_DmaCfgAndUse_Impl/).

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

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

Related artefacts kept in their native format (not converted):
- `CM200C_DmaCfgAndUse_Design/Design/CM200C_DmaCfgAndUse_NexteerDmaRegsh.xlsx`
- `CM200C_DmaCfgAndUse_Design/Design/CM200C_DmaCfgAndUse_PeripheralCfg.xlsx`
- `CM200C_DmaCfgAndUse_Design/Doc/CM200C_DmaCfgAndUse_FDD_Checklist.xlsx`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [CM200C_DmaCfgAndUse_Impl](../CM200C_DmaCfgAndUse_Impl/) and the sources themselves.
- Short name `DmaCfgAndUse` (code `CM200C`) is retained for traceability; prose on this page uses the expanded long name.
