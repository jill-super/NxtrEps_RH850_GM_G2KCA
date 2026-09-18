---
title: "Non-Volatile Random Access Memory Manager (NvM)"
description: "The NVRAM Manager ensure the data storage and maintenance of NV data"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

The NVRAM Manager ensure the data storage and maintenance of NV data. 
This module delivers Non-Volatile Random Access Memory Manager for the controller.

*AUTOSAR layer: Basic Software Services. Origin: Vector-provided.*

## Key files

- C sources: **6**, headers: **8** (counts from a repository scan).
- Principal sources: `src/NvM.c`, `src/NvM_Act.c`, `src/NvM_Crc.c`, `src/NvM_JobProc.c`, `src/NvM_Qry.c`, `src/NvM_Queue.c`
- Principal headers: `include/NvM.h`, `include/NvM_Act.h`, `include/NvM_Cbk.h`, `include/NvM_Crc.h`, `include/NvM_JobProc.h`, `include/NvM_Qry.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `NvM.h`; main source: `NvM.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Non-volatile memory handling for calibration data
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_NvM.pdf](./TechnicalReference-NvM/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `NvM/doc/NvM Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `NvM` (code `NvM`) is retained for traceability; prose on this page uses the expanded long name.
