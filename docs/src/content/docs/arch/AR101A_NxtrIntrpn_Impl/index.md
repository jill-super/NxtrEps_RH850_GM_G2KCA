---
title: "Nexteer Interpolation Library (AR101A_NxtrIntrpn_Impl)"
description: "Source file for the interpolation library"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Source file for the interpolation library. 
This is the **implementation** folder for Nexteer Interpolation Library (NxtrIntrpn); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [AR101A_NxtrIntrpn_Design](../AR101A_NxtrIntrpn_Design/).

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **2** (counts from a repository scan).
- Principal sources: `src/NxtrIntrpn.c`
- Principal headers: `include/NxtrIntrpn.h`, `include/NxtrIntrpn_MemMap.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `NxtrIntrpn.h`; main source: `NxtrIntrpn.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [NxtrIntrpn Integration Manual.doc](./NxtrIntrpn-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `AR101A_NxtrIntrpn_Impl/doc/NxtrIntrpn Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [AR101A_NxtrIntrpn_Design](../AR101A_NxtrIntrpn_Design/) and the sources themselves.
- Short name `NxtrIntrpn` (code `AR101A`) is retained for traceability; prose on this page uses the expanded long name.
