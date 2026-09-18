---
title: "Watchdog Manager (WdgM)"
description: "This file contains a trusted function interface for WdgM_Init. This is currently needed because"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

This file contains a trusted function interface for WdgM_Init. This is currently needed because. 
This module delivers Watchdog Manager for the controller.

*AUTOSAR layer: Basic Software Services. Origin: Vector-provided.*

## Key files

- C sources: **3**, headers: **9** (counts from a repository scan).
- Principal sources: `src/NxtrWdgM.c`, `src/WdgM.c`, `src/WdgM_Checkpoint.c`
- Principal headers: `generate/WdgM_Verifier/wdgm_verifier.h`, `generate/WdgM_Verifier/wdgm_verifier_types.h`, `generate/WdgM_Verifier/wdgm_verifier_version.h`, `include/NxtrWdgM.h`, `include/WdgM.h`, `include/WdgM_Cfg.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/NxtrWdgM.h`, `tools/contract/WdgM.h`, `tools/contract/WdgM_PBcfg.h`
- Main header: `wdgm_verifier.h`; main source: `NxtrWdgM.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

5 document(s) beside the code were converted to Markdown pages in this folder:
- [S-WdgM_ReleaseNotes.pdf](./S-WdgM-ReleaseNotes/) — Release Notes
- [S-WdgM_SafetyManual.pdf](./S-WdgM-SafetyManual/) — Safety Manual / Safety Case
- [S-WdgM_Stack_SafetyCase.pdf](./S-WdgM-Stack-SafetyCase/) — Safety Manual / Safety Case
- [S-WdgM_UserManual.pdf](./S-WdgM-UserManual/) — User Manual / User Guide
- [WdgM Integration Manual.doc](./WdgM-Integration-Manual/) — Integration Manual

Related artefacts kept in their native format (not converted):
- `WdgM/doc/WdgM Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `WdgM` (code `WdgM`) is retained for traceability; prose on this page uses the expanded long name.
