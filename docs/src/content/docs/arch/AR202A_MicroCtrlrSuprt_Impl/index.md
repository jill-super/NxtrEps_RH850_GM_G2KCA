---
title: "Microcontroller Support (AR202A_MicroCtrlrSuprt_Impl)"
description: "Nexteer Microcontroller Unit Support Library Header"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Nexteer Microcontroller Unit Support Library Header. 
This is the **implementation** folder for Microcontroller Support (MicroCtrlrSuprt); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Architecture Libraries and Platform Support. Origin: Custom (in-house).*

## Key files

- C sources: **1**, headers: **45** (counts from a repository scan).
- Principal headers: `include/P1M/NxtrMcuSuprtLib.h`, `include/P1M/R7F701311/adcd_regs.h`, `include/P1M/R7F701311/ecc_regs.h`, `include/P1M/R7F701311/flash_regs.h`, `include/P1M/R7F701311/ipg_regs.h`, `include/P1M/R7F701311/ostm_regs.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `tools/contract/CDD_ExcpnHndlg.h`, `tools/contract/NxtrMcuSuprtLib_TestHarness.h`
- Main header: `NxtrMcuSuprtLib.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

Related artefacts kept in their native format (not converted):
- `AR202A_MicroCtrlrSuprt_Impl/doc/MicroCtrlrSuprt Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `MicroCtrlrSuprt` (code `AR202A`) is retained for traceability; prose on this page uses the expanded long name.
