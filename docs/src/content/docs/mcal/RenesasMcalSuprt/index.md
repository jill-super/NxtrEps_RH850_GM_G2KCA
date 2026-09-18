---
title: "Renesas Microcontroller Abstraction Support (RenesasMcalSuprt)"
description: "Renesas Extensions to Compiler.h. Since the Nexteer has multiple vendors currently providing a"
badge:
  text: "Renesas-provided"
  variant: "note"
---

:::note
**Renesas-provided driver.** Microcontroller vendor delivery for the RH850 family; project code configures and calls it rather than modifying it.
:::

## Purpose and responsibility

Renesas Extensions to Compiler.h. Since the Nexteer has multiple vendors currently providing a. 
This module delivers Renesas Microcontroller Abstraction Support for the controller.

*AUTOSAR layer: Microcontroller Abstraction Layer. Origin: Renesas-provided.*

## Key files

- C sources: **0**, headers: **7** (counts from a repository scan).
- Principal headers: `include/P1M/4.00.04/Renesas_Compiler.h`, `include/P1M/4.00.04/rh850_Types.h`, `include/P1M/E4.03/rh850_Types.h`, `tools/P1M/4.00.04/Compiler.h`, `tools/P1M/4.00.04/Compiler_Cfg.h`, `tools/P1M/4.00.04/Platform_Types.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `Renesas_Compiler.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Microcontroller hardware via the vendor driver named on this page
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

5 document(s) beside the code were converted to Markdown pages in this folder:
- [GettingStarted_MCAL_Drivers_X1x.pdf](./GettingStarted-MCAL-Drivers-X1x/) — Portable Document (vendor or generated report)
- [KnownIssues_P1x_R403_2015_CW23.pdf](./KnownIssues-P1x-R403-2015-CW23/) — Portable Document (vendor or generated report)
- [Releasenotes_P1x_FULL_R403_Ver4.00.04.pdf](./Releasenotes-P1x-FULL-R403-Ver4-00-04/) — Release Notes
- [readme.txt](./readme/) — Text Note / Report
- [readme.txt](./readme-2/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `RenesasMcalSuprt/doc/RenesasMcalSuprt Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `RenesasMcalSuprt` (code `RenesasMcalSuprt`) is retained for traceability; prose on this page uses the expanded long name.
