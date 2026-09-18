---
title: "Universal Measurement and Calibration Protocol (Xcp)"
description: "Implementation of the XCP Protocol Layer"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Implementation of the XCP Protocol Layer. 
This module delivers Universal Measurement and Calibration Protocol for the controller.

*AUTOSAR layer: Basic Software Communication Stack. Origin: Vector-provided.*

## Key files

- C sources: **3**, headers: **2** (counts from a repository scan).
- Principal sources: `src/XcpProf.c`, `src/xcp_can.c`
- Principal headers: `include/XcpProf.h`, `include/xcp_can.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `XcpProf.h`; main source: `XcpProf.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

4 document(s) beside the code were converted to Markdown pages in this folder:
- [TechnicalReference_XCP_Protocol_Layer.pdf](./TechnicalReference-XCP-Protocol-Layer/) — Technical Reference (vendor)
- [TechnicalReference_XCP_on_CAN.pdf](./TechnicalReference-XCP-on-CAN/) — Technical Reference (vendor)
- [UserManual_XCP.pdf](./UserManual-XCP/) — User Manual / User Guide
- [Xcp Integration Manual.doc](./Xcp-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `Xcp/doc/Xcp Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Xcp` (code `Xcp`) is retained for traceability; prose on this page uses the expanded long name.
