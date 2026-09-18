---
title: "Vector Basic Software Support Library (VectorBswSuprt)"
description: "Lowlevel part of the implementation of standard Vector functions"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Lowlevel part of the implementation of standard Vector functions. 
This module delivers Vector Basic Software Support Library for the controller.

*AUTOSAR layer: Basic Software Services. Origin: Vector-provided.*

## Key files

- C sources: **4**, headers: **5** (counts from a repository scan).
- Principal sources: `src/01.03.00_03.08.00/vstdlib.c`, `src/01.04.00_03.08.00/vstdlib.c`, `src/02.00.00/vstdlib.c`, `src/02.00.02/vstdlib.c`
- Principal headers: `include/01.03.00_03.08.00/vstdlib.h`, `include/01.04.00_03.08.00/vstdlib.h`, `include/02.00.00/vstdlib.h`, `include/02.00.02/vstdlib.h`, `tools/template/02.00.00/_VStdLib_Cfg.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `vstdlib.h`; main source: `vstdlib.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

5 document(s) beside the code were converted to Markdown pages in this folder:
- [AN-ISC-2-1081_Interrupt_Control_VStdLib.pdf](./AN-ISC-2-1081-Interrupt-Control-VStdLib/) — Portable Document (vendor or generated report)
- [TechnicalReference_VStdLib.pdf](./TechnicalReference-VStdLib/) — Technical Reference (vendor)
- [TechnicalReference_VStdLib_GenericAsr.pdf](./TechnicalReference-VStdLib-GenericAsr/) — Technical Reference (vendor)
- [TechnicalReference_VStdLib_GenericAsr.pdf](./TechnicalReference-VStdLib-GenericAsr-2/) — Technical Reference (vendor)
- [VectorBswSuprt Integration Manual.doc](./VectorBswSuprt-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `VectorBswSuprt/doc/VectorBswSuprt Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `VectorBswSuprt` (code `VectorBswSuprt`) is retained for traceability; prose on this page uses the expanded long name.
