---
title: "AUTOSAR layers"
description: "How repository folders map to AUTOSAR layers."
---
## Layering used in this documentation

| Layer | Contains | Typical folder prefixes |
|---|---|---|
| Application Software | Steering functions (Assist, Return, Damping, Stability Compensation and similar), customer vehicle functions, serial communication message proxies, motor velocity control | Steering Function, Customer Function, Message Manager, Motor Velocity Control |
| Complex Device Drivers | Microcontroller peripheral configuration and usage, sensor measurement, power, temperature, gate-driver and motor-driver handling, fault injection | Microcontroller Configuration, Electronic Sensing, Diagnostic Fault Injection |
| Architecture Libraries | Shared mathematics, interpolation, time, fixed-point, filtering, AUTOSAR support shims, global parameters | Architecture |
| Basic Software Services | Operating system, controller state management, mode management, memory management, diagnostic event handling, watchdog management, manufacturing services | Operating System, Controller State Manager, Non-Volatile Memory, Diagnostic Event Manager |
| Communication Stack | Interaction layer, transport protocol, network management, diagnostic addon, calibration protocol, General Motors network handler | Interaction Layer, Transport Protocol, Network Management |
| Microcontroller Abstraction | Vendor drivers for digital input-output, ports, serial interfaces, flash, watchdog, controller area network, microcontroller unit | Microcontroller, Digital Input Output, Serial Peripheral Interface |
| Electronic Control Unit Abstraction | Input-output hardware abstraction, memory abstraction interface, flash emulation, watchdog interface, controller configuration | Hardware Abstraction, Memory Interface |
| Runtime Environment | Generated runnable backbone, contracts, and memory mapping | Runtime Environment |
| Tools | Generators, checkers, scripts, viewers, Python utilities | Tooling |
| Integration | Top-level controller build, checkpoints, part numbers, customer diagnostics | Platform Integration |

### Design versus Implementation folders

Many logical components appear twice: a `..._Design` folder holding the functional design artefacts and a `..._Impl` folder holding the compilable implementation. Each folder has its own page so the artefacts stay traceable; the two pages link to each other where both exist.

### Assumption log

- Electronic Sensing components (power, temperature, current, angle, voltage) are grouped under Complex Device Drivers because they touch hardware directly, even though a few of them (system state mode, diagnostic manager, calibration interface) also play service roles. Their pages state both aspects.
- Manufacturing service components are grouped under Basic Software Services.
- The top-level controller build and platform identification components are grouped under Integration.
