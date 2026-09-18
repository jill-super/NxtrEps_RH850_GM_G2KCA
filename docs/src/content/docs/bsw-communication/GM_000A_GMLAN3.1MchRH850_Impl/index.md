---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 (GM_000A_GMLAN3.1MchRH850_Impl)"
description: "* 1) Check that all currently compiled files in the system have the correct"
badge:
  text: "Vector-provided"
  variant: "caution"
---

:::caution
**Vector-provided module.** Third-party delivery — do not hand-edit sources or generated files; change configuration and regenerate instead.
:::

## Purpose and responsibility

* 1) Check that all currently compiled files in the system have the correct. 
This is the **implementation** folder for General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 (000A_GMLAN3.1MchRH850); it holds the compilable sources, AUTOSAR descriptors, generation contracts, and tool projects.

*AUTOSAR layer: Basic Software Communication Stack. Origin: Vector-provided.*

## Key files

- C sources: **1**, headers: **2** (counts from a repository scan).
- Principal sources: `src/sip_vers.c`
- Principal headers: `include/sip_vers.h`, `include/v_def.h`
- Also present: `tools/` Green Hills project files and generation contracts; design and integration notes beside the code (converted below where convertible).

## Public interface and usage

- Main header: `sip_vers.h`; main source: `sip_vers.c`.
- Callers reach this component through the Runtime Environment (runnables, sender-receiver ports) and, for driver wrappers, through the wrapped vendor driver interface.
- Typical integration: configure the component in DaVinci, regenerate the contracts, add the component project to the top-level Green Hills build, and connect its ports in the system model. Error reporting follows the project convention via the Development Error Tracer and Diagnostic Event Manager hooks where the component provides them.

## Dependencies

- Operating System (scheduling of the containing task)
- Development Error Tracer and Diagnostic Event Manager for error classification where applicable

## Documents

17 document(s) beside the code were converted to Markdown pages in this folder:
- [2392.0_ADD_Nexteer_CBD_GMLAN_31_Mch_Renesas RH850 -CBD1400346.D01.pdf](./2392-0-ADD-Nexteer-CBD-GMLAN-31-Mch-Renesas-RH850-CBD1400346-D01/) — Portable Document (vendor or generated report)
- [AN-IND-8-003_GM_Support_in_CANoe_7.2.pdf](./AN-IND-8-003-GM-Support-in-CANoe-7-2/) — Portable Document (vendor or generated report)
- [AN-ISC-2-1011_CANfblGM_CALL_From_CANdesc.pdf](./AN-ISC-2-1011-CANfblGM-CALL-From-CANdesc/) — Portable Document (vendor or generated report)
- [AN-ISC-2-1052_CANbedded_and_Operating_Systems.pdf](./AN-ISC-2-1052-CANbedded-and-Operating-Systems/) — Portable Document (vendor or generated report)
- [AN-ISC-8-1056_CANbedded_Program_Stack_Usage.pdf](./AN-ISC-8-1056-CANbedded-Program-Stack-Usage/) — Portable Document (vendor or generated report)
- [AN-ISC-8-1074_Possible_Loss_Of_Wakeup_Message.pdf](./AN-ISC-8-1074-Possible-Loss-Of-Wakeup-Message/) — Portable Document (vendor or generated report)
- [CANdelaStudio_Gm_contact.PDF](./CANdelaStudio-Gm-contact/) — Portable Document (vendor or generated report)
- [GMLAN3.1MchRH850 Integration Manual.doc](./GMLAN3-1MchRH850-Integration-Manual/) — Integration Manual
- [IssueReport_CBD1400346.pdf](./IssueReport-CBD1400346/) — Portable Document (vendor or generated report)
- [TechnicalReference_CANdesc.pdf](./TechnicalReference-CANdesc/) — Technical Reference (vendor)
- [TechnicalReference_CANdesc_KWP_GM.pdf](./TechnicalReference-CANdesc-KWP-GM/) — Technical Reference (vendor)
- [TechnicalReference_Database_Attributes_GM.pdf](./TechnicalReference-Database-Attributes-GM/) — Technical Reference (vendor)
- [TechnicalReference_GMLANCalibration.pdf](./TechnicalReference-GMLANCalibration/) — Technical Reference (vendor)
- [UserManual_CANdesc.pdf](./UserManual-CANdesc/) — User Manual / User Guide
- [UserManual_CANoe_Model_Generator.pdf](./UserManual-CANoe-Model-Generator/) — User Manual / User Guide
- [UserManual_Startup_with_GMLAN_GENy.pdf](./UserManual-Startup-with-GMLAN-GENy/) — User Manual / User Guide
- [readme.txt](./readme/) — Text Note / Report

Related artefacts kept in their native format (not converted):
- `GM_000A_GMLAN3.1MchRH850_Impl/doc/DeliveryDescription_CBD1400346.html`
- `GM_000A_GMLAN3.1MchRH850_Impl/doc/DeliveryTestReport_CBD1400346.html`
- `GM_000A_GMLAN3.1MchRH850_Impl/doc/GM_000A_GMLAN3.1MchRH850_Impl Peer Review Checklists.xlsm`

## Notes and assumptions

- Page generated from a repository scan: file counts, file names, and header banners are factual; behavioural detail beyond the converted notes comes from the design folder and the sources themselves.
- Short name `000A_GMLAN3.1MchRH850` (code `GM`) is retained for traceability; prose on this page uses the expanded long name.
