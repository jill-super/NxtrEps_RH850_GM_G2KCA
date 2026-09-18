---
title: "Flash Memory Driver (Fls)"
description: "Descriptor variable definition"
badge:
  text: "Renesas-provided"
  variant: "note"
---

:::note
**Renesas-provided driver.** Microcontroller vendor delivery for the RH850 family; project code configures and calls it rather than modifying it.
:::

## Purpose and responsibility

Descriptor variable definition. 
This module delivers Flash Memory Driver for the controller.

*AUTOSAR layer: Microcontroller Abstraction Layer. Origin: Renesas-provided.*

## Key files

- C sources: **9**, headers: **30** (counts from a repository scan).
- Principal sources: `src/Fls.c`, `src/Fls_Internal.c`, `src/Fls_Irq.c`, `src/Fls_Ram.c`, `src/fdl_descriptor.c`, `src/r_fdl_hw_access.c`
- Principal headers: `include/Fls_Debug.h`, `include/Fls_Irq.h`, `include/Fls_PBTypes.h`, `include/Fls_Types.h`, `include/Fls_Version.h`, `include/r_fdl.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `Fls_Debug.h`; main source: `Fls.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AUTOSAR_FLS_Component_UserManual.pdf](./AUTOSAR-FLS-Component-UserManual/) — User Manual / User Guide
- [AUTOSAR_FLS_Tool_UserManual.pdf](./AUTOSAR-FLS-Tool-UserManual/) — User Manual / User Guide

Related artefacts kept in their native format (not converted):
- `Fls/doc/Fls Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Fls` (code `Fls`) is retained for traceability; prose on this page uses the expanded long name.
