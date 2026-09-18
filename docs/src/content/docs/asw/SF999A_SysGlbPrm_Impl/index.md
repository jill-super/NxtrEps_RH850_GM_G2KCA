---
title: "System Global Parameters (SF999A_SysGlbPrm_Impl)"
description: "System global parameter definitions"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

System global parameter definitions. 
This is the **implementation** folder for System Global Parameters (SysGlbPrm); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects. The functional design artefacts live in [SF999A_SysGlbPrm_Design](../SF999A_SysGlbPrm_Design/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **1** (counts from a repository scan).
- Principal headers: `include/SysGlbPrm.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `SysGlbPrm.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

Related artefacts kept in their native format (not converted):
- `SF999A_SysGlbPrm_Impl/doc/SysGlbPrm Review.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF999A_SysGlbPrm_Design](../SF999A_SysGlbPrm_Design/) and the sources themselves.
- Short name `SysGlbPrm` (code `SF999A`) is retained for traceability; prose on this page uses the expanded long name.
