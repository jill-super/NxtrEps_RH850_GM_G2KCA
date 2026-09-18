---
title: "Transport Protocol (ISO 15765-2) (Tp)"
description: "This version supports the specification for"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

This version supports the specification for. 
This module delivers Transport Protocol (ISO 15765-2) for the controller.

*AUTOSAR layer: Basic Software Communication Stack. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **1** (counts from a repository scan).
- Principal sources: `src/tpmc.c`
- Principal headers: `include/tpmc.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `tpmc.h`; main source: `tpmc.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_TransportProtocolMultiConnection.pdf](./TechnicalReference-TransportProtocolMultiConnection/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `Tp/doc/Tp Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Tp` (code `Tp`) is retained for traceability; prose on this page uses the expanded long name.
