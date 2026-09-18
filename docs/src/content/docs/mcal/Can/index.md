---
title: "Controller Area Network Driver (Can)"
description: "Application interface of the CAN driver"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Application interface of the CAN driver. 
This module delivers Controller Area Network Driver for the controller.

*AUTOSAR layer: Microcontroller Abstraction Layer. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **2** (counts from a repository scan).
- Principal sources: `src/can_drv.c`
- Principal headers: `include/can_def.h`, `tools/templates/_can_inc.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `can_def.h`; main source: `can_drv.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

4 document(s) beside the code were converted to Markdown pages in this folder:
- [Can Integration Manual.doc](./Can-Integration-Manual/) — Integration Manual
- [TechnicalReference_CANDriver.pdf](./TechnicalReference-CANDriver/) — Technical Reference (vendor)
- [TechnicalReference_Rh850_Rscan.pdf](./TechnicalReference-Rh850-Rscan/) — Technical Reference (vendor)
- [UserManual_CanDriver.pdf](./UserManual-CanDriver/) — User Manual / User Guide

Related artefacts kept in their native format (not converted):
- `Can/doc/Can Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Can` (code `Can`) is retained for traceability; prose on this page uses the expanded long name.
