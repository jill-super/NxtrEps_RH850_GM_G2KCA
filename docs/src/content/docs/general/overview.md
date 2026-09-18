---
title: "Project overview"
description: "What this controller project is and how the documentation is organised."
---
## What this project is

This repository implements a complete Electric Power Steering controller for a General Motors passenger-vehicle platform, running on a Renesas RH850 microcontroller. The software follows the AUTOSAR Classic architecture (version 4.0.3 artefacts are stored beside the components), uses the Vector MICROSAR communication stack with DaVinci and GENy configuration, and is built with the Green Hills MULTI toolchain (each component ships a `.gpj` project file).

## How the documentation is organised

Content mirrors the AUTOSAR layering, one folder per layer, one subfolder per repository module:

| Layer folder | Long name | Modules |
|---|---|---:|
| `asw` | Application Software | 150 |
| `cdd` | Complex Device Drivers and Sensor-Actuator Components | 130 |
| `arch` | Architecture Libraries and Platform Support | 18 |
| `bsw-services` | Basic Software Services | 14 |
| `bsw-communication` | Basic Software Communication Stack | 7 |
| `mcal` | Microcontroller Abstraction Layer | 8 |
| `ecu-abstraction` | Electronic Control Unit Abstraction Layer | 5 |
| `rte` | Runtime Environment | 1 |
| `tools` | Auxiliary Tools and Configuration | 11 |
| `integration` | System Integration and Platform | 4 |

That is **348 module folders** in total. The [module matrix](./module-matrix/) lists every folder with its layer and origin, and each module page uses expanded long names (for example “Assist” rather than the bare short name “Assi”) with the original short name kept in parentheses for traceability.

## Reading guide

1. New readers start here, then read [AUTOSAR layers](./architecture-layers/) and [Third-party versus in-house code](./vector-vs-custom/).
2. Builders read [Build system](./build-system/) and [Deployment](./deployment/).
3. Safety and quality readers see [Safety and quality](./safety-and-quality/).
4. Component readers pick a layer and open a module page; converted design notes sit beside it.
