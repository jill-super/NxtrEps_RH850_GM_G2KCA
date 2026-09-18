---
title: "Electronic Control Unit State Manager (EcuM)"
description: "This EcuM.h provides the API functionality provided by the ASR4 EcuM Flexible"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

This EcuM.h provides the API functionality provided by the ASR4 EcuM Flexible. 
This module delivers Electronic Control Unit State Manager for the controller.

*AUTOSAR layer: Basic Software Services. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **3** (counts from a repository scan).
- Principal sources: `src/EcuM.c`
- Principal headers: `include/EcuM.h`, `include/EcuM_Cbk.h`, `include/EcuM_Error.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `EcuM.h`; main source: `EcuM.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_EcuM.pdf](./TechnicalReference-EcuM/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `EcuM/doc/EcuM Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `EcuM` (code `EcuM`) is retained for traceability; prose on this page uses the expanded long name.
