---
title: "Runtime Environment (Rte)"
description: "Runtime Environment (Rte) for the Electric Power Steering controller"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Runtime Environment (Rte) for the Electric Power Steering controller. 
This module delivers Runtime Environment for the controller.

*AUTOSAR layer: Runtime Environment. Origin: Vector-provided.*

## Key files

- C sources: **0**, headers: **0** (counts from a repository scan).
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Interface is delivered through the Runtime Environment contracts and configuration listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

5 document(s) beside the code were converted to Markdown pages in this folder:
- [SafetyGuide_Rte.pdf](./SafetyGuide-Rte/) — Safety Manual / Safety Case
- [TechnicalReference_Rte.pdf](./TechnicalReference-Rte/) — Technical Reference (vendor)
- [License_Apache-2.0.txt](./License-Apache-2-0/) — Text Note / Report
- [License_Artistic.txt](./License-Artistic/) — Text Note / Report
- [License_JamesNewton-King.txt](./License-JamesNewton-King/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `Rte/doc/ReleaseNotes_MICROSAR_RTE.htm`
- `Rte/doc/Rte Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Rte` (code `Rte`) is retained for traceability; prose on this page uses the expanded long name.
