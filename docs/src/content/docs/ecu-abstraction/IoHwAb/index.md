---
title: "Input Output Hardware Abstraction (IoHwAb)"
description: "The IO Hardware Abstraction provides the transitions of signals from the MCAL layer to the upper"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

The IO Hardware Abstraction provides the transitions of signals from the MCAL layer to the upper. 
This module delivers Input Output Hardware Abstraction for the controller.

*AUTOSAR layer: Electronic Control Unit Abstraction Layer. Origin: Vector-provided.*

## Key files

- C sources: **0**, headers: **1** (counts from a repository scan).
- Principal headers: `include/IoHwAb.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `IoHwAb.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_IoHwAb.pdf](./TechnicalReference-IoHwAb/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `IoHwAb/doc/IoHwAb Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `IoHwAb` (code `IoHwAb`) is retained for traceability; prose on this page uses the expanded long name.
