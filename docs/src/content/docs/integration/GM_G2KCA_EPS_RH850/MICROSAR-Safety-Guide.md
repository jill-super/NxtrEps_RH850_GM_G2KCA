---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — MICROSAR Safety Guide"
description: "Converted Safety Manual / Safety Case from MICROSAR_Safety_Guide.pdf (PDF, 893 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/SafetyManuals/MICROSAR_Safety_Guide.pdf` (Safety Manual / Safety Case; original PDF, about 893 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR 
Safety Guide 
 
 
Version 1.2.2 
 
 
 
 
 
 
 
 
 
 
 
Authors Jonas Wolf 
Status Released

--- Page 2 ---
Safety Guide MICROSAR 
2014, Vector Informatik GmbH Version: 1.2.2 
based on template version 5.7.1 
2 / 37 
Document Information 
History 
Author Date Version Remarks 
Jonas Wolf 2014-01-08 0.1.0 Initial structure 
Jonas Wolf 2014-01-27 0.2.0 Ready for review 
Jonas Wolf 2014-01-31 0.2.1 First comments included 
Jonas Wolf 2014-02-06 0.2.2 Review comments from visml included 
Jonas Wolf 2014-02-07 0.2.3 Added additional AUTOSAR components 
Jonas Wolf 2014-02-17 0.2.4 Rework after review sessions 
Jonas Wolf 2014-03-10 0.3.0 Rework after review with visrn 
Jonas Wolf 2014-03-28 1.0.0 Final rework and release 
Jonas Wolf 2014-05-27 1.1.0 Improvements from workshop with 
customer 
Jonas Wolf 2014-06-03 1.2.0 Rework after review with visml 
Jonas Wolf 2014-10-14 1.2.1 Clarifications on section 2.3 
Jonas Wolf 2014-10-20 1.2.2 More information on securing non-volatile 
data

--- Page 3 ---
Safety Guide MICROSAR 
2014, Vector Informatik GmbH Version: 1.2.2 
based on template version 5.7.1 
3 / 37 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_TR_SafetyConceptStatusReport.pdf V1.2.0 
[2]  AUTOSAR AUTOSAR_SWS_CRCLibrary.pdf V4.4.0 
[3]  AUTOSAR AUTOSAR_SWS_ECUStateManager.pdf V4.1.0 
[4]  AUTOSAR AUTOSAR_SWS_E2ELibrary.pdf V3.1.0 
[5]  Vector MICROSAR RTE 
Safety Guide 
SafetyGuide_Rte.pdf 
V4.2.0 
[6]  Boeing Single Event Upset at Ground Level 
Eugene Normand, 
Boeing Defense & Space Group, Seattle, WA 98124-2499 
2004 
[7]  ISO ISO 26262-4:2011 
Road vehicles — Functional safety — Product development at 
the system level 
2011 
[8]  ISO ISO 26262-5:2011 
Road vehicles — Functional safety — Product development at 
the hardware level 
2011 
[9]  ISO ISO 26262-6:2011 
Road vehicles — Functional safety — Product development at 
the software level 
2011 
[10]  Koopman 32-Bit Cyclic Redundancy Codes for Internet Applications 
Philip Koopman, 
ECE Department & ICES, Carnegie Mellon University, 
Pittsburgh, PA, USA 
2002 
[11]  IEEE IEEE Std 802.3™-2012 2012 
[12]  TTTech Safe Watchdog Manager 
Safety Manual 
D-SAFEX-S-70-001 
2.3.9 
[13]  TTTech Safe Watchdog Interface 
Safety Manual 
D-SAFEX-S-70-005 
1.8.3 
[14]  TTTech E2E Protection Wrapper 
Safety Manual 
D-MSP-M-70-002 
1.2.9

--- Page 4 ---
Safety Guide MICROSAR 
2014, Vector Informatik GmbH Version: 1.2.2 
based on template version 5.7.1 
4 / 37 
Contents 
1 Introduction................................ ................................ ................................ ................... 7 
1.1 Purpose ................................ ................................ ................................ ............. 7 
1.2 Scope ................................ ................................ ................................ ................ 7 
1.3 Definitions ................................ ................................ ................................ .......... 7 
1.4 Overview ................................ ................................ ................................ ............ 8 
2 Functional safety on system level ................................ ................................ ............... 9 
2.1 Prevention of unintended behavior ................................ ................................ ..... 9 
2.2 Mitigation of risk associated with a failure ................................ ........................ 10 
2.3 Fail-safe and fail-operational systems ................................ ..............................  11 
3 Recommendations on safety mechanisms ................................ ...............................  12 
3.1 Integrity of the microcontroller ................................ ................................ .......... 12 
3.1.1 Operation in lock-step mode ................................ ............................ 12 
3.1.2 Monitoring the temperature of the microcontrollers .......................... 12 
3.1.3 Self-test of the microcontroller components ................................ ..... 12 
3.2 Integrity of volatile data ................................ ................................ .................... 13 
3.2.1 Static tests of volatile memory ................................ .......................... 13 
3.2.1.1 Initial test of volatile memory ................................ .......... 13 
3.2.1.2 Periodic tests of volatile memory ................................ .... 14 
3.2.2 Protection of volatile memory through error correcting codes (ECC) 14 
3.2.2.1 Redundant storage of data ................................ ............. 14 
3.3 Integrity of non-volatile data ................................ ................................ ............. 15 
3.3.1 Consistency of configuration and calibration data ............................ 15 
3.3.2 Securing non-volatile data with use of NVRAM Manager ................. 16 
3.4 Initialization of the microcontroller ................................ ................................ .... 17 
3.5 Separation in memory ................................ ................................ ...................... 18 
3.6 Separation in time ................................ ................................ ............................ 19 
3.7 Scheduling ................................ ................................ ................................ ....... 20 
3.8 Communication ................................ ................................ ................................  21 
3.9 Input and output ................................ ................................ ...............................  21 
4 Example use-cases ................................ ................................ ................................ ..... 22 
4.1 ECU with direct I/O ................................ ................................ .......................... 22 
4.2 ECU with direct I/O and safety-related bus communication ..............................  24 
4.3 Mixed ASIL SWCs with safety-related bus communication ...............................  25 
5 Recommendations for the MICROSAR stack ................................ ........................... 27 
5.1 Initialization ................................ ................................ ................................ ...... 27

--- Page 5 ---
Safety Guide MICROSAR 
2014, Vector Informatik GmbH Version: 1.2.2 
based on template version 5.7.1 
5 / 37 
5.2 ECU State Manager (EcuM) ................................ ................................ ............ 27 
5.3 Basic Software Mode Manager (BswM) ................................ ........................... 27 
5.4 Development Error Tracer (Det) ................................ ................................ ....... 27 
5.5 Diagnostic Event Manager (Dem) ................................ ................................ .... 28 
5.6 NVRAM Manager ................................ ................................ ............................. 28 
5.7 Run-Time Environment (RTE) ................................ ................................ .......... 28 
5.8 End-to-End Protection (E2E) ................................ ................................ ............ 28 
5.9 Operating System (OS) ................................ ................................ .................... 28 
5.10 Interrupt service routines (ISRs) ................................ ................................ ....... 28 
5.11 Microcontroller Abstraction Layer (MCAL) ................................ ........................ 29 
6 Procedural requirements ................................ ................................ ........................... 30 
7 Assumptions of Vector’s safety solution ................................ ................................ .. 31 
7.1 Assumptions of RTE ................................ ................................ ........................ 31 
7.2 Assumptions of SafeWatchdog ................................ ................................ ........ 34 
8 Glossary and Abbreviations ................................ ................................ ...................... 36 
8.1 Glossary ................................ ................................ ................................ .......... 36 
8.2 Abbreviations ................................ ................................ ................................ ... 36 
9 Contact ................................ ................................ ................................ ........................ 37

--- Page 6 ---
Safety Guide MICROSAR 
2014, Vector Informatik GmbH Version: 1.2.2 
based on template version 5.7.1 
6 / 37 
Illustrations 
Figure 2-1 Relation between test depth, system functionality and residual faults ......... 9 
Figure 3-1 Example for protecting non-volatile memory with two CRCs ..................... 15 
Figure 3-2 Establishing consistency of multiple data block groups ......

[… 31 further page(s) not extracted …]
