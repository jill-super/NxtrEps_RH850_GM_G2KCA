---
title: "Return (SF002A_Rtn_Design)"
description: "Return (Rtn) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic.
:::

## Purpose and responsibility

Return (Rtn) for the Electric Power Steering controller. 
This is the **functional design** folder for Return (Rtn); the compilable sources live in the sibling implementation folder [SF002A_Rtn_Impl](../SF002A_Rtn_Impl/).

*AUTOSAR layer: Application Software. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **0** (counts from a repository scan).
- Also present: design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Interface is delivered through the Runtime Environment contracts and configuration listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

1 document(s) beside the code were converted to Markdown pages in this folder:
- [SF002A_Rtn_DDReport.txt](./SF002A-Rtn-DDReport/) — Design Document / Report

Related artefacts kept in their native format (not converted):
- `SF002A_Rtn_Design/Doc/SF002A_Rtn_Peer Review Checklist Design.xlsx`
- `SF002A_Rtn_Design/Reports/SF002A_Rtn_modeladvisor.html`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder [SF002A_Rtn_Impl](../SF002A_Rtn_Impl/) and the sources themselves.
- Short name `Rtn` (code `SF002A`) is retained for traceability; prose on this page uses the expanded long name.
