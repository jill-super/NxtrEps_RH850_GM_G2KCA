---
title: "Coupler Support Tooling (TL103A_CplrSuprt)"
description: "Coupler Support Tooling (CplrSuprt) for the Electric Power Steering controller"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

Coupler Support Tooling (CplrSuprt) for the Electric Power Steering controller. 
This module delivers Coupler Support Tooling for the controller.

*AUTOSAR layer: Auxiliary Tools and Configuration. Origin: Custom (in-house).*

## Key files

- C sources: **0**, headers: **80** (counts from a repository scan).
- Principal headers: `include/2015.1.5/ansi/fenv.h`, `include/2015.1.5/ansi/ghs_null.h`, `include/2015.1.5/ansi/ghs_wchar.h`, `include/2015.1.5/ansi/limits.h`, `include/2015.1.5/ansi/math.h`, `include/2015.1.5/ansi/signal.h`
- Also present: `tools/` Green Hills project files and generation contracts.

## Public interface and usage

- Runtime Environment contracts: `tools/contract/PolyspaceEnvironment.h`
- Main header: `fenv.h`; main source: `see source list`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

No convertible Word, Portable Document Format, or text notes were found directly beside this module.

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `CplrSuprt` (code `TL103A`) is retained for traceability; prose on this page uses the expanded long name.
