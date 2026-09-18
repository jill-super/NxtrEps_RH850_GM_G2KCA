---
title: "Watchdog Driver (Wdg)"
description: "Watchdog Driver (Wdg) for the Electric Power Steering controller"
badge:
  text: "Renesas-provided"
  variant: "note"
---

:::note
**Renesas-provided driver.** Microcontroller vendor delivery for the RH850 family; project code configures and calls it rather than modifying it.
:::

## Purpose and responsibility

Watchdog Driver (Wdg) for the Electric Power Steering controller. 
This module delivers Watchdog Driver for the controller.

*AUTOSAR layer: Microcontroller Abstraction Layer. Origin: Renesas-provided.*

## Key files

- C sources: **5**, headers: **24** (counts from a repository scan).
- Principal sources: `src/Wdg_59_DriverA.c`, `src/Wdg_59_DriverA_Irq.c`, `src/Wdg_59_DriverA_Private.c`, `src/Wdg_59_DriverA_Ram.c`, `src/Wdg_59_DriverA_Version.c`
- Principal headers: `generate/dr7f701315_0.h`, `include/Wdg_59_DriverA.h`, `include/Wdg_59_DriverA_Debug.h`, `include/Wdg_59_DriverA_Irq.h`, `include/Wdg_59_DriverA_PBTypes.h`, `include/Wdg_59_DriverA_Private.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `dr7f701315_0.h`; main source: `Wdg_59_DriverA.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AUTOSAR_WDG_Component_UserManual.pdf](./AUTOSAR-WDG-Component-UserManual/) — User Manual / User Guide
- [AUTOSAR_WDG_Tool_UserManual.pdf](./AUTOSAR-WDG-Tool-UserManual/) — User Manual / User Guide

Related artefacts kept in their native format (not converted):
- `Wdg/doc/Wdg Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Wdg` (code `Wdg`) is retained for traceability; prose on this page uses the expanded long name.
