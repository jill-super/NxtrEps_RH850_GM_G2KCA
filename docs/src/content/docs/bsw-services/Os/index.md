---
title: "Operating System (Os)"
description: "Nexteer OS Error Handling function"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Nexteer OS Error Handling function. 
This module delivers Operating System for the controller.

*AUTOSAR layer: Basic Software Services. Origin: Vector-provided.*

## Key files

- C sources: **15**, headers: **20** (counts from a repository scan).
- Principal sources: `src/atosappl.c`, `src/osek.c`, `src/osekalrm.c`, `src/osekevnt.c`, `src/osekrsrc.c`, `src/oseksched.c`
- Principal headers: `include/Os.h`, `include/Os_Cfg.h`, `include/osDerivatives.h`, `include/osekasm.h`, `include/osekasrt.h`, `include/osekerr.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/NxtrOsErrHndlg.h`, `tools/contract/Os.h`
- Main header: `Os.h`; main source: `atosappl.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

7 document(s) beside the code were converted to Markdown pages in this folder:
- [MicrosarOS_RH850_SafeContext_SafetyManual.pdf](./MicrosarOS-RH850-SafeContext-SafetyManual/) — Safety Manual / Safety Case
- [Os Integration Manual.doc](./Os-Integration-Manual/) — Integration Manual
- [Os Module Design Document.docx](./Os-Module-Design-Document/) — Design / Integration Document
- [ProductInformation_2_Restrictions-for-MSR-OS-SafeContext-SC3.pdf](./ProductInformation-2-Restrictions-for-MSR-OS-SafeContext-SC3/) — Portable Document (vendor or generated report)
- [ReleaseNotes_Microsar_Os.txt](./ReleaseNotes-Microsar-Os/) — Release Notes
- [TechnicalReference_MICROSAROS_RH850.pdf](./TechnicalReference-MICROSAROS-RH850/) — Technical Reference (vendor)
- [TechnicalReference_Os.pdf](./TechnicalReference-Os/) — Technical Reference (vendor)

Related artefacts kept in their native format (not converted):
- `Os/doc/Os Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Os` (code `Os`) is retained for traceability; prose on this page uses the expanded long name.
