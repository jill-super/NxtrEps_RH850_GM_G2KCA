---
title: "Operating System — TechnicalReference Os"
description: "Converted Technical Reference (vendor) from TechnicalReference_Os.pdf (PDF, 3089 KB)."
---

:::note
Converted from `Os/doc/TechnicalReference_Os.pdf` (Technical Reference (vendor); original PDF, about 3089 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Os](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR OS SafeContext 
Technical Reference 
 
 
Version 9.01 
 
 
 
 
 
 
 
 
 
Status Released 
Document ID OS01.0280

--- Page 2 ---
Technical Reference MICROSAR OS SafeContext   
2015, Vector Informatik GmbH Version: 9.01 
based on template version 4.3 
2 / 136 
Document Information 
History 
Author Date Version Remarks 
Rmk 2012-06-26 6.00 creation based on AUTOSAR 3.0 version 
Shk 2013-09-18 6.01 SingleSource template applied and 
variants for ASR3.x, ASR4.x, SafeContext 
and non-SafeContext prepared 
Biv 2014-02-04 6.02 MultiCore references corrected 
Zfa 2014-05-05 6.03 Updated timer description 
Asl 2014-08-14 8.00 Examples chapter excluded 
TimingAnalyzer removed 
Updated counter related macros and 
configuration  
Asl 2014-10-16 8.01 Added PeripheralRegion API 
Added Non-Trusted Function API 
Added CheckMPUAccess API 
Asl 2015-01-29 9.00 Updated interpretation of 
OsSecondsPerTick and 
OsCounterTicksPerBase 
Rk 2015-06-17 9.01 Added MICROSAR OS Timing Hooks 
Added table of terms to the glossary 
Added the information that forcible 
termination is currently not supported

--- Page 3 ---
Technical Reference MICROSAR OS SafeContext   
2015, Vector Informatik GmbH Version: 9.01 
based on template version 4.3 
3 / 136 
Reference Documents 
No. Title Version 
[1]  AUTOSAR_SWS_OS.pdf 
AUTOSAR OS specification; This document is available in PDF-format on the 
internet a the AUTOSAR homepage (http://www.autosar.org) 
V5.0.0 
[2]  AUTOSAR_TR_BSWModuleList.pdf 1.6.0 
[3]  OSEK/VDX Operating System Specification 
This document is available in PDF-format on the Internet at the OSEK/VDX 
homepage (http://www.osek-vdx.org) 
2.2.3 
[4]  TechincalReference_Microsar_Os_Multicore.pdf 1.00 
[5]  TechnicalReference_MicrosarOS_xxxx.pdf 
Technical reference of Vector MICROSAR OS; Hardware specific part 
-- 
[6]  OIL: OSEK Implementation Language 
This document is available in PDF-format on the Internet at the OSEK/VDX 
homepage (http://www.osek-vdx.org) 
2.3 
[7]  Tutorial_osCAN.pdf 
Tutorial for the MICROSAR OS OSEK/AUTOSAR Realtime Operating System 
1.00 
[8]  autosar.xsd 
AUTOSAR XML schema 
4.0.3 
[9]  MicrosarOS_xxxx_SafeContext_SafetyManual.pdf 
Application Conditions for SEooC; Implementation specific document 
-- 
Scope of the Document 
MICROSAR OS is an operating system, comp liant with the AUTOSAR OS and OSEK 
standards. The general aspects of all SafeContext implementations are described in this 
document. For each implementation, the hardware specific part is described in a separate 
document [4]. 
The implementation is based on the AUTOSAR OS specification [1]. 
It is also based on the OSEK OS specification 2.2 described in the document [3]. 
As a SEooC, it is further based on assumptions regarding safety requirements. Details can 
be found in [9]. 
This documentation assumes that the reader is familiar with both the OSEK OS 
specification and the AUTOSAR OS specification. 
This documentation describes only the operating system and the code generation tool. 
OSEK is a registered trademark of Continental Automotive GmbH (until 2007: Siemens 
AG).

--- Page 4 ---
Technical Reference MICROSAR OS SafeContext   
2015, Vector Informatik GmbH Version: 9.01 
based on template version 4.3 
4 / 136 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 5 ---
Technical Reference MICROSAR OS SafeContext   
2015, Vector Informatik GmbH Version: 9.01 
based on template version 4.3 
5 / 136 
Contents 
1 Component History ................................ ................................ ................................ ...... 14 
2 Introduction ................................ ................................ ................................ .................. 15 
2.1 Architecture Overview ................................ ................................ ................... 15 
3 Functional Description ................................ ................................ ................................  17 
3.1 Features ................................ ................................ ................................ ........ 17 
3.2 Main Functions ................................ ................................ ..............................  17 
3.2.1 Timer and Alarms ................................ ................................ .......................... 18 
3.2.1.1 Time Base ................................ ................................ ................................ ..... 19 
3.2.1.1.1 Counter Macros ................................ ................................ ............................. 19 
3.2.1.1.2 Temporal Range of Alarms ................................ ................................ ............ 19 
3.2.1.2 Timer Interrupt Routine ................................ ................................ .................. 19 
3.2.1.2.1 Counter API ................................ ................................ ................................ ... 19 
3.2.2 Stack Handling ................................ ................................ ..............................  20 
3.2.2.1 Task Stack ................................ ................................ ................................ ..... 20 
3.2.2.2 Interrupt Stack ................................ ................................ ...............................  20 
3.2.2.3 Stack Monitoring ................................ ................................ ............................ 21 
3.2.2.4 Stack Usage ................................ ................................ ................................ .. 21 
3.2.3 Interrupt Handling ................................ ................................ .......................... 21 
3.2.3.1 Interrupt Categories................................ ................................ ....................... 22 
3.2.3.1.1 Category 1: ................................ ................................ ................................ ... 22 
3.2.3.1.2 Category 2: ................................ ................................ ................................ ... 22 
3.2.3.2 Usage of the Interrupt API before StartOS ................................ ..................... 23 
3.2.4 Timing Protection ................................ ................................ .......................... 24 
3.2.4.1 Reaction on Protection Failure ................................ ................................ ...... 24 
3.2.4.2 Timing Measurement ................................ ................................ ..................... 24 
3.2.4.2.1 Timing measurement configuration for a specific task/ISR ............................ 25 
3.2.4.2.2 Global configuration of timing measurement ................................ ................. 25 
3.2.4.3 Hook functions ................................ ................................ ..............................  26 
3.2.5 Memory Protection ................................ ................................ ........................ 26 
3.2.6 Schedule Tables ................................ ................................ ............................ 27 
3.2.6.1 Synchronization ................................ ................................ ............................. 27 
3.2.6.1.1 Starting a synchronizable Schedule Table .................

--- Page 6 ---
Technical Reference MICROSAR OS SafeContext   
2015, Vector Informatik GmbH Version: 9.01 
based on template version 4.3 
6 / 136 
3.2.6.1.6 Limits of the Synchronization Algorithm ................................ ......................... 29 
3.2.6.1.7 Details about using NextScheduleTable ................................ ........................ 30 
3.2.6.1.8 Concurrent Actions ................................ ................................ ........................ 30 
3.2.6.2 High-Resolution Schedule Tables ................................ ................................ .. 30 
3.2.6.2.1 Setup ................................ ................................ ................................ ............ 31 
3.2.6.3 Cyclical Expiry Point Actions ................................ ................................ ......... 31 
3.2.7 Trusted Functions ................................ ................................ .......................... 31 
3.2.7.1 Generated Stub Functions ................................ ................................ ............. 31 
3.3 Error Handling ................................ ................................ ...............................  33 
3.3.1 Error Messages ................................ ................................ ............................. 33 
3.3.2 OSEK / AUTOS

[… 130 further page(s) not extracted …]
