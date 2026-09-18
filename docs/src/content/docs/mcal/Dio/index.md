---
title: "Digital Input Output Driver (Dio)"
description: "Digital Input Output Driver (Dio) for the Electric Power Steering controller"
badge:
  text: "Renesas-provided"
  variant: "note"
---

:::note
**Renesas-provided driver.** Microcontroller vendor delivery for the RH850 family; project code configures and calls it rather than modifying it.
:::

## Purpose and responsibility

Digital Input Output Driver (Dio) for the Electric Power Steering controller. 
This module delivers Digital Input Output Driver for the controller.

*AUTOSAR layer: Microcontroller Abstraction Layer. Origin: Renesas-provided.*

## Key files

- C sources: **3**, headers: **21** (counts from a repository scan).
- Principal sources: `src/Dio.c`, `src/Dio_Ram.c`, `src/Dio_Version.c`
- Principal headers: `generate/P1x_translation.h`, `generate/dr7f701314_0.h`, `generate/dr7f701315_0.h`, `generate/dr7f701318_0.h`, `include/Dio.h`, `include/Dio_Debug.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `P1x_translation.h`; main source: `Dio.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AUTOSAR_DIO_Component_UserManual.pdf](./AUTOSAR-DIO-Component-UserManual/) — User Manual / User Guide
- [AUTOSAR_DIO_Tool_UserManual.pdf](./AUTOSAR-DIO-Tool-UserManual/) — User Manual / User Guide

Related artefacts kept in their native format (not converted):
- `Dio/doc/Dio Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Dio` (code `Dio`) is retained for traceability; prose on this page uses the expanded long name.
