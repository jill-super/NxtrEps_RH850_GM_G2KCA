---
title: "Temperature Monitoring (ES005A_TmplMonr_Design)"
description: "Temperature Monitoring (TmplMonr) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Temperature Monitoring (TmplMonr) for the Electric Power Steering controller. 
This is the **functional design** folder for Temperature Monitoring (TmplMonr); the compilable sources live in the sibling implementation folder [ES005A_TmplMonr_Impl](../ES005A_TmplMonr_Impl/).

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

4 document(s) beside the code were converted to Markdown pages in this folder:
- [A4412 WD State Diagram 2015_06_09.pdf](./A4412-WD-State-Diagram-2015-06-09/) — Portable Document (vendor or generated report)
- [ES005 TmplMonr Requirements.pdf](./ES005-TmplMonr-Requirements/) — Requirements Export
- [Temporal Monitor Operation - Graphical Representation.pdf](./Temporal-Monitor-Operation-Graphical-Representation/) — Portable Document (vendor or generated report)
- [ES005A_TmplMonr_DDReport.txt](./ES005A-TmplMonr-DDReport/) — Design Document / Report

Related artefacts kept in their native format (not converted):
- `ES005A_TmplMonr_Design/Doc/WATCHDOG_CALC_ANALYSIS__NM_01OC14___NEW.xlsx`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [ES005A_TmplMonr_Impl](../ES005A_TmplMonr_Impl/) and the sources themselves.
- Short name `TmplMonr` (code `ES005A`) is retained for traceability; prose on this page uses the expanded long name.
