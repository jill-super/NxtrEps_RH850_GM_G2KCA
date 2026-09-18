---
title: "Watchdog Interface (WdgIf)"
description: "Watchdog Interface (WdgIf) for the Electric Power Steering controller"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Watchdog Interface (WdgIf) for the Electric Power Steering controller. 
This module delivers Watchdog Interface for the controller.

*AUTOSAR layer: Electronic Control Unit Abstraction Layer. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **3** (counts from a repository scan).
- Principal sources: `src/WdgIf.c`
- Principal headers: `include/WdgIf.h`, `include/WdgIf_Cfg.h`, `include/WdgIf_Types.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `WdgIf.h`; main source: `WdgIf.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

4 document(s) beside the code were converted to Markdown pages in this folder:
- [S-WdgIf_ReleaseNotes.pdf](./S-WdgIf-ReleaseNotes/) — Release Notes
- [S-WdgIf_SafetyCase.pdf](./S-WdgIf-SafetyCase/) — Safety Manual / Safety Case
- [S-WdgIf_SafetyManual.pdf](./S-WdgIf-SafetyManual/) — Safety Manual / Safety Case
- [S-WdgIf_UserManual.pdf](./S-WdgIf-UserManual/) — User Manual / User Guide

Related artefacts kept in their native format (not converted):
- `WdgIf/doc/WdgIf Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `WdgIf` (code `WdgIf`) is retained for traceability; prose on this page uses the expanded long name.
