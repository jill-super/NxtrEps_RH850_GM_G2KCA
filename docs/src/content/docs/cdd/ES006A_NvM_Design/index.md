---
title: "Non-Volatile M (ES006A_NvM_Design)"
description: "Non-Volatile M (NvM) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Non-Volatile M (NvM) for the Electric Power Steering controller. 
This is the **functional design** folder for Non-Volatile M (NvM); the compilable sources live in the sibling implementation folder [ES006A_NvM_Impl](../ES006A_NvM_Impl/).

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
- Non-volatile memory handling for calibration data
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

7 document(s) beside the code were converted to Markdown pages in this folder:
- [jquery-license.txt](./jquery-license/) — Text Note / Report
- [jquery-highlight-license.txt](./jquery-highlight-license/) — Text Note / Report
- [jquery-nanoscroller-license.txt](./jquery-nanoscroller-license/) — Text Note / Report
- [jquery-ui-license.txt](./jquery-ui-license/) — Text Note / Report
- [respond-license.txt](./respond-license/) — Text Note / Report
- [ES006A_NvM_FDD.docx](./ES006A-NvM-FDD/) — Design / Integration Document
- [ES006A_NvM_DDReport.txt](./ES006A-NvM-DDReport/) — Design Document / Report

Related artefacts kept in their native format (not converted):
- `ES006A_NvM_Design/Design/Library/Documentation/EraseBlock.html`
- `ES006A_NvM_Design/Design/Library/Documentation/GetErrorStatus.html`
- `ES006A_NvM_Design/Design/Library/Documentation/InvalidateBlock.html`
- `ES006A_NvM_Design/Design/Library/Documentation/ReadBlock.html`
- `ES006A_NvM_Design/Design/Library/Documentation/RestoreBlockDefaults.html`
- `ES006A_NvM_Design/Design/Library/Documentation/SetBlockProtection.html`
- `ES006A_NvM_Design/Design/Library/Documentation/SetRamBlockStatus.html`
- `ES006A_NvM_Design/Design/Library/Documentation/WriteBlock.html`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES006A_NvM_Impl](../ES006A_NvM_Impl/) and the sources themselves.
- Short name `NvM` (code `ES006A`) is retained for traceability; prose on this page uses the expanded long name.
