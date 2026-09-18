---
title: "Component Runtime Environment Generator Support (TL101A_CptRteGen)"
description: "Component Runtime Environment Generator Support (CptRteGen) for the Electric Power Steering controller"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

Component Runtime Environment Generator Support (CptRteGen) for the Electric Power Steering controller. 
This module delivers Component Runtime Environment Generator Support for the controller.

*AUTOSAR layer: Auxiliary Tools and Configuration. Origin: Vector-provided.*

## Key files

- C sources: **0**, headers: **0** (counts from a repository scan).
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Interface is delivered through the Runtime Environment contracts and configuration listed above.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

34 document(s) beside the code were converted to Markdown pages in this folder:
- [CptRteGenNotes.txt](./CptRteGenNotes/) — Text Note / Report
- [DVCfg_AutomationInterfaceDocumentation.pdf](./DVCfg-AutomationInterfaceDocumentation/) — Portable Document (vendor or generated report)
- [antlr2-license.txt](./antlr2-license/) — Text Note / Report
- [asm-license.txt](./asm-license/) — Text Note / Report
- [eclipse-license.txt](./eclipse-license/) — Text Note / Report
- [gradle-license.txt](./gradle-license/) — Text Note / Report
- [groovy-license.txt](./groovy-license/) — Text Note / Report
- [guava-license.txt](./guava-license/) — Text Note / Report
- [hamcrest-license.txt](./hamcrest-license/) — Text Note / Report
- [jline2-license.txt](./jline2-license/) — Text Note / Report
- [jsr223-license.txt](./jsr223-license/) — Text Note / Report
- [junit-license.txt](./junit-license/) — Text Note / Report
- [log4j2-license.txt](./log4j2-license/) — Text Note / Report
- [normalize-stylesheet-license.txt](./normalize-stylesheet-license/) — Text Note / Report
- [spock-license.txt](./spock-license/) — Text Note / Report
- [AUTHORS.txt](./AUTHORS/) — Text Note / Report
- [CHANGES.txt](./CHANGES/) — Text Note / Report
- [LICENSE.txt](./LICENSE/) — Text Note / Report
- [README-license.txt](./README-license/) — Text Note / Report
- [README.txt](./README/) — Text Note / Report
- [LICENSE-2.0.txt](./LICENSE-2-0/) — Text Note / Report
- [README.txt](./README-2/) — Text Note / Report
- [THIRDPARTYLICENSEREADME-JAVAFX.txt](./THIRDPARTYLICENSEREADME-JAVAFX/) — Text Note / Report
- [THIRDPARTYLICENSEREADME.txt](./THIRDPARTYLICENSEREADME/) — Text Note / Report
- [Xusage.txt](./Xusage/) — Text Note / Report
- [jvm.hprof.txt](./jvm-hprof/) — Text Note / Report
- [README.txt](./README-3/) — Text Note / Report
- [THIRDPARTYLICENSEREADME-JAVAFX.txt](./THIRDPARTYLICENSEREADME-JAVAFX-2/) — Text Note / Report
- [THIRDPARTYLICENSEREADME.txt](./THIRDPARTYLICENSEREADME-2/) — Text Note / Report
- [Xusage.txt](./Xusage-2/) — Text Note / Report
- [jvm.hprof.txt](./jvm-hprof-2/) — Text Note / Report
- [License_Apache-2.0.txt](./License-Apache-2-0/) — Text Note / Report
- [License_Artistic.txt](./License-Artistic/) — Text Note / Report
- [License_JamesNewton-King.txt](./License-JamesNewton-King/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.emf.common_2.12.0.v20160420-0247/epl-v10.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.emf.common_2.12.0.v20160420-0247/license.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.graphiti.feature_0.13.0.v20160608-1043/epl-v10.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.graphiti.feature_0.13.0.v20160608-1043/license.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.help_2.2.0.v20160606-1100/epl-v10.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/features/org.eclipse.help_2.2.0.v20160606-1100/license.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/plugins/org.eclipse.jdt.debug_3.10.0.v20160418-1524/about.html`
- `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/x86_64/jre/Welcome.html`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `CptRteGen` (code `TL101A`) is retained for traceability; prose on this page uses the expanded long name.
