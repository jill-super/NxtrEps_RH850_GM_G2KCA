---
title: "Microcontroller Error Injection (DF003A_McuErrInj_Impl)"
description: "Micro Diag Error Injection header file"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Micro Diag Error Injection header file. 
This is the **implementation** folder for Microcontroller Error Injection (McuErrInj); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Complex Device Drivers and Sensor-Actuator Components. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **1** (counts from a repository scan).
- Principal headers: `include/McuErrInj.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `McuErrInj.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

Related artefacts kept in their native format (not converted):
- `DF003A_McuErrInj_Impl/doc/McuErrInj_Design_Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `McuErrInj` (code `DF003A`) is retained for traceability; prose on this page uses the expanded long name.
