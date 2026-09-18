---
title: "Diagnostic Gateway Addon (Diag)"
description: "GM Gateway Diagnostic Addon"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

GM Gateway Diagnostic Addon. 
This module delivers Diagnostic Gateway Addon for the controller.

*AUTOSAR layer: Basic Software Communication Stack. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **1** (counts from a repository scan).
- Principal sources: `src/ggda.c`
- Principal headers: `include/ggda.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `ggda.h`; main source: `ggda.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_GGDA.pdf](./TechnicalReference-GGDA/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `Diag/doc/Diag Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Diag` (code `Diag`) is retained for traceability; prose on this page uses the expanded long name.
