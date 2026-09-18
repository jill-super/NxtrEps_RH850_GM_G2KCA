---
title: "Flash EEPROM Emulation (Fee)"
description: "The module Fee provides an abstraction from the device specific addressing scheme and"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

The module Fee provides an abstraction from the device specific addressing scheme and. 
This module delivers Flash EEPROM Emulation for the controller.

*AUTOSAR layer: Electronic Control Unit Abstraction Layer. Origin: Vector-provided.*

## Key files

- C sources: **4**, headers: **8** (counts from a repository scan).
- Principal sources: `src/Fee.c`, `src/Fee_ChunkInfo.c`, `src/Fee_Partition.c`, `src/Fee_Sector.c`
- Principal headers: `include/Fee.h`, `include/Fee_Cbk.h`, `include/Fee_ChunkInfo.h`, `include/Fee_Int.h`, `include/Fee_IntBase.h`, `include/Fee_Partition.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `Fee.h`; main source: `Fee.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

2 document(s) beside the code were converted to Markdown pages in this folder:
- [AN-ISC-8-1161_FEE_alignments_to_reduce_data_loss_through_ECC.pdf](./AN-ISC-8-1161-FEE-alignments-to-reduce-data-loss-through-ECC/) — Portable Document (vendor or generated report)
- [TechnicalReference_Fee.pdf](./TechnicalReference-Fee/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `Fee/doc/Fee Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Fee` (code `Fee`) is retained for traceability; prose on this page uses the expanded long name.
