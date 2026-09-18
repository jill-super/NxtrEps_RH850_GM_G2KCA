---
title: "Hex File Viewer Tooling (TL106A_HexView)"
description: "Hex File Viewer Tooling (HexView) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Hex File Viewer Tooling (HexView) for the Electric Power Steering controller. 
This module delivers Hex File Viewer Tooling for the controller.

*AUTOSAR layer: Auxiliary Tools and Configuration. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **0** (counts from a repository scan).
- Also present: `tools/` Green Hills project files and generation contracts.

## Public interface and usage

- Interface is delivered through the Runtime Environment contracts and configuration listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [ReferenceManual_HexView.pdf](./ReferenceManual-HexView/) — Portable Document (vendor or generated report)
- [disclaimer.txt](./disclaimer/) — Text Note / Report

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `HexView` (code `TL106A`) is retained for traceability; prose on this page uses the expanded long name.
