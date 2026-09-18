---
title: "Safety and quality"
description: "Functional-safety and quality notes."
---
## Safety context

The controller is developed against automotive functional-safety practice (ASIL D processes are referenced by the watchdog manager safety manual and stack safety case in this repository). Safety-relevant mechanisms visible in the tree include the watchdog manager with its safety manual, critical-register verification, clock monitoring, data and address parity handling, dual-controller identification, and loss-of-assist management.

## Quality artefacts

Each component folder may carry peer-review checklists, requirements exports, and static-analysis result folders (quality-assurance tool results and Polyspace result folders). The converted documentation pages preserve these references and mark spreadsheet or tool-database artefacts as related rather than converted, since tabular checklists do not convert faithfully to prose.
