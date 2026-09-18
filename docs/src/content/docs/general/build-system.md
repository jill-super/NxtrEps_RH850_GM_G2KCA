---
title: "Build system"
description: "How the controller firmware is built."
---
## Toolchain

- **Compiler and debugger:** Green Hills MULTI. Every compilable component ships a `.gpj` project file under its `tools/` folder, and the top-level controller project aggregates them (`generate.gpj`, `src.gpj`, `include.gpj`, plus per-variant project files for the two controller instances and their combination).
- **Configuration:** DaVinci Configurator (software-component and Basic Software configuration) and GENy (network configuration). Generated artefacts (`generate/` folders, RTE contracts, memory-mapping headers) are checked in beside the hand-written code.
- **Target:** Renesas RH850 family, with linker command files stored in the top-level project tools folder.

## Typical build flow

1. Edit the DaVinci or GENy model and regenerate the affected component (never hand-edit generated files).
2. Open the top-level Green Hills project and build the controller variant required (first instance, second instance, or combined).
3. Run the static-analysis and requirements checks documented alongside each component (quality-assurance results folders sit next to the sources).

## Host-side utilities

The `tools` layer holds host-side helpers (component Runtime Environment generation support, coupler support, architecture tooling, hex viewer, common checks, Python utilities, manufacturing-service support). These run on the workstation, not on the controller, and are documented as tools rather than firmware.
