---
title: "Nexteer Detection Library (AR998A_NxtrDet_Impl)"
description: "Nexteer Det Configuration"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Nexteer Det Configuration. 
This is the **implementation** folder for Nexteer Detection Library (NxtrDet); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [AR998A_NxtrDet_Design](../AR998A_NxtrDet_Design/).

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **1** (counts from a repository scan).
- Principal headers: `include/NxtrDet.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `NxtrDet.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

3 document(s) beside the code were converted to Markdown pages in this folder:
- [AR998A_NxtrDet_DDReport.txt](./AR998A-NxtrDet-DDReport/) — Design Document / Report
- [NxtrDet Integration Manual.doc](./NxtrDet-Integration-Manual/) — Integration Manual
- [NxtrDet Module Design Document.docx](./NxtrDet-Module-Design-Document/) — Design / Integration Document

Related artefacts kept in their native format (not converted):
- `AR998A_NxtrDet_Impl/doc/NxtrDet Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [AR998A_NxtrDet_Design](../AR998A_NxtrDet_Design/) and the sources themselves.
- Short name `NxtrDet` (code `AR998A`) is retained for traceability; prose on this page uses the expanded long name.
