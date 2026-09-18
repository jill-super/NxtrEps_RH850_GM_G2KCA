---
title: "DaVinci Configuration Support (TL102A_Davinci)"
description: "DaVinci Configuration Support (Davinci) for the Electric Power Steering controller"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

DaVinci Configuration Support (Davinci) for the Electric Power Steering controller. 
This module delivers DaVinci Configuration Support for the controller.

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

15 document(s) beside the code were converted to Markdown pages in this folder:
- [AN-ISC-8-1102_IdentityManager_MultipleECUs.pdf](./AN-ISC-8-1102-IdentityManager-MultipleECUs/) — Portable Document (vendor or generated report)
- [ApplicationNotes_DifferenceAnalyzer.pdf](./ApplicationNotes-DifferenceAnalyzer/) — Portable Document (vendor or generated report)
- [LicenseManagerHelp.pdf](./LicenseManagerHelp/) — Portable Document (vendor or generated report)
- [TechnicalReference_AutoConnect.pdf](./TechnicalReference-AutoConnect/) — Technical Reference (vendor)
- [TechnicalReference_DataTypes_AR4.pdf](./TechnicalReference-DataTypes-AR4/) — Technical Reference (vendor)
- [TechnicalReference_EcuConfigurationFiles.pdf](./TechnicalReference-EcuConfigurationFiles/) — Technical Reference (vendor)
- [TechnicalReference_UserDefinedAttributeExport.pdf](./TechnicalReference-UserDefinedAttributeExport/) — Technical Reference (vendor)
- [UserManual_DataImport.pdf](./UserManual-DataImport/) — User Manual / User Guide
- [UserManual_Working_with_DCF.pdf](./UserManual-Working-with-DCF/) — User Manual / User Guide
- [LICENSE.txt](./LICENSE/) — Text Note / Report
- [README.txt](./README/) — Text Note / Report
- [THIRDPARTYLICENSEREADME.txt](./THIRDPARTYLICENSEREADME/) — Text Note / Report
- [Xusage.txt](./Xusage/) — Text Note / Report
- [Xusage.txt](./Xusage-2/) — Text Note / Report
- [jvm.hprof.txt](./jvm-hprof/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `TL102A_Davinci/tools/Developer/Docs/ReadmeInstall.htm`
- `TL102A_Davinci/tools/Developer/Docs/ReleaseNotes.htm`
- `TL102A_Davinci/tools/Developer/Reporting/jre/Welcome.html`
- `TL102A_Davinci/tools/Developer/Reporting/plugins/org.eclipse.birt.report.engine.fonts_3.7.2.v20120213/about.html`
- `TL102A_Davinci/tools/Developer/Reporting/plugins/org.eclipse.core.runtime.compatibility.registry_3.5.0.v20110505/about.html`
- `TL102A_Davinci/tools/Developer/Reporting/plugins/org.eclipse.equinox.launcher.win32.win32.x86_1.1.100.v20110502/about.html`
- `TL102A_Davinci/tools/Developer/Reporting/plugins/org.w3c.sac_1.3.0.v20120213/about.html`
- `TL102A_Davinci/tools/Developer/Reporting/plugins/org.w3c.sac_1.3.0.v20120213/about_files/copyright-software-20021231.htm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `Davinci` (code `TL102A`) is retained for traceability; prose on this page uses the expanded long name.
