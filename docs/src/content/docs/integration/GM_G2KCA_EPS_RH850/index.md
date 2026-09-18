---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) (GM_G2KCA_EPS_RH850)"
description: "BSWM Callout Functions"
badge:
  text: "Custom (in-house)"
  variant: "success"
---

:::tip
**Custom (in-house) module.** Project-developed logic. Runtime scaffolding in this folder was produced by the Vector MICROSAR Runtime Environment generator and should be regenerated rather than hand-edited.
:::

## Purpose and responsibility

BSWM Callout Functions. 
This module delivers Top-Level Controller Project (G2KCA Electric Power Steering on RH850) for the controller.

*AUTOSAR layer: System Integration and Platform. Origin: Custom (in-house).*

## Key files

- C sources: **77**, headers: **715** (counts from a repository scan).
- Principal sources: `generate/Dio/src/Dio_PBcfg.c`, `generate/Fls/src/Fls_PBcfg.c`, `generate/Mcu/src/Mcu_PBcfg.c`, `generate/Port/src/Port_PBcfg.c`, `generate/Spi/src/Spi_Lcfg.c`, `generate/Spi/src/Spi_PBcfg.c`
- Principal headers: `include/ComM.h`, `include/ComM_EcuMBswM.h`, `include/ComM_Types.h`, `include/DualEcuSelect.h`, `include/MemDef.h`, `include/MemMap.h`
- Also present: `autosar/` descriptors (component, datatypes, port interfaces); `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Runtime Environment contracts: `generate/Rte_Cbk.h`, `generate/Rte_Cfg.h`, `generate/Rte_Compiler_Cfg.h`, `generate/Rte_DataHandleType.h`, `generate/Rte_Main.h`, `generate/Rte_MemMap.h`
- Main header: `ComM.h`; main source: `IoHwAb_30.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Runtime Environment (generated contracts and memory mapping)
- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

47 document(s) beside the code were converted to Markdown pages in this folder:
- [BetaDisclaimer.txt](./BetaDisclaimer/) — Text Note / Report
- [BoostReadMe.txt](./BoostReadMe/) — Text Note / Report
- [Boost_LICENSE_1_0.txt](./Boost-LICENSE-1-0/) — Text Note / Report
- [Expat_COPYING.txt](./Expat-COPYING/) — Text Note / Report
- [MSPublic.txt](./MSPublic/) — Text Note / Report
- [STLport_LICENSE.txt](./STLport-LICENSE/) — Text Note / Report
- [Unzip_LICENSE.txt](./Unzip-LICENSE/) — Text Note / Report
- [Xerces_3.1_Apache_LICENSE.txt](./Xerces-3-1-Apache-LICENSE/) — Text Note / Report
- [Zip_LICENSE.txt](./Zip-LICENSE/) — Text Note / Report
- [AUTHORS.txt](./AUTHORS/) — Text Note / Report
- [CHANGES.txt](./CHANGES/) — Text Note / Report
- [LICENSE.txt](./LICENSE/) — Text Note / Report
- [README-license.txt](./README-license/) — Text Note / Report
- [README.txt](./README/) — Text Note / Report
- [ASL-LICENSE-2.0.txt](./ASL-LICENSE-2-0/) — Text Note / Report
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
- [AN-ISC-8-1153_ThirdPartyModules.pdf](./AN-ISC-8-1153-ThirdPartyModules/) — Portable Document (vendor or generated report)
- [AN-ISC-8-1170_Use_AR3_SWCs_in_AR4.pdf](./AN-ISC-8-1170-Use-AR3-SWCs-in-AR4/) — Portable Document (vendor or generated report)
- [2242.0_LUA_Nexteer_MSR_GM_Renesas RH850-CBD1400351.D03.pdf](./2242-0-LUA-Nexteer-MSR-GM-Renesas-RH850-CBD1400351-D03/) — Portable Document (vendor or generated report)
- [IssueReport_CBD1400351.pdf](./IssueReport-CBD1400351/) — Portable Document (vendor or generated report)
- [ProductInformation_2_MICROSAR_SoftwarePackagesAndMaintenance.pdf](./ProductInformation-2-MICROSAR-SoftwarePackagesAndMaintenance/) — Portable Document (vendor or generated report)
- [ReleaseNotes_3rdPartyMCAL_VectorIntegration.pdf](./ReleaseNotes-3rdPartyMCAL-VectorIntegration/) — Release Notes
- [MICROSAR_Safety_Guide.pdf](./MICROSAR-Safety-Guide/) — Safety Manual / Safety Case
- [SafetyManual.pdf](./SafetyManual/) — Safety Manual / Safety Case
- [Startup_GM_SLP2.pdf](./Startup-GM-SLP2/) — Portable Document (vendor or generated report)
- [TechnicalReference_3rdParty-MCAL-Integration.pdf](./TechnicalReference-3rdParty-MCAL-Integration/) — Technical Reference (vendor)
- [TechnicalReference_Asr_MemoryMapping.pdf](./TechnicalReference-Asr-MemoryMapping/) — Technical Reference (vendor)
- [TechnicalReference_Cdd.pdf](./TechnicalReference-Cdd/) — Technical Reference (vendor)
- [TechnicalReference_ComStackLib.pdf](./TechnicalReference-ComStackLib/) — Technical Reference (vendor)
- [TechnicalReference_DaVinciConfigurator_Licenses.pdf](./TechnicalReference-DaVinciConfigurator-Licenses/) — Technical Reference (vendor)
- [TechnicalReference_DiagA2lGen.pdf](./TechnicalReference-DiagA2lGen/) — Technical Reference (vendor)
- [TechnicalReference_ExternalDependenciesOfGenerators.pdf](./TechnicalReference-ExternalDependenciesOfGenerators/) — Technical Reference (vendor)
- [TechnicalReference_GenTool_CsAsrLegacyDb2SystemDescr_Vector.pdf](./TechnicalReference-GenTool-CsAsrLegacyDb2SystemDescr-Vector/) — Technical Reference (vendor)
- [TechnicalReference_MSSV.pdf](./TechnicalReference-MSSV/) — Technical Reference (vendor)
- [TechnicalReference_SipModificationChecker.pdf](./TechnicalReference-SipModificationChecker/) — Technical Reference (vendor)
- [DocumentationGuide_VectorAUTOSAR.pdf](./DocumentationGuide-VectorAUTOSAR/) — Portable Document (vendor or generated report)
- [license python 2_7.txt](./license-python-2-7/) — Text Note / Report
- [rsakeys_2048.txt](./rsakeys-2048/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `GM_G2KCA_EPS_RH850/generate/EnadMfgSrvRef.html`
- `GM_G2KCA_EPS_RH850/generate/Os_ECUC_4.0.3.arxml.htm`
- `GM_G2KCA_EPS_RH850/generate/Rte.html`
- `GM_G2KCA_EPS_RH850/tools/SIP/DaVinciConfigurator/Core/features/org.eclipse.emf.common_2.10.1.v20150123-0348/license.html`
- `GM_G2KCA_EPS_RH850/tools/SIP/Doc/DeliveryInformation/DeliveryDescription_CBD1400351.html`
- `GM_G2KCA_EPS_RH850/tools/SIP/Doc/ReleaseNotes/ReleaseNotes_Cfg4.htm`
- `GM_G2KCA_EPS_RH850/tools/SIP/Doc/ReleaseNotes/ReleaseNotes_DaVinciConfigurator.html`
- `GM_G2KCA_EPS_RH850/tools/VrfyCritRegGen/RH850 Static Register Evaluation - T1xx.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `G2KCA_EPS_RH850` (code `GM`) is retained for traceability; prose on this page uses the expanded long name.
