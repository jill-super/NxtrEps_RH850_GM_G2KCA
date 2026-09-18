---
title: "Electronic Control Unit State Manager — TechnicalReference EcuM"
description: "Converted Technical Reference (vendor) from TechnicalReference_EcuM.pdf (PDF, 2655 KB)."
---

:::note
Converted from `EcuM/doc/TechnicalReference_EcuM.pdf` (Technical Reference (vendor); original PDF, about 2655 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to EcuM](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR EcuM Flex 
Technical Reference 
 
SysService_Asr4EcuM 
Version 5.00.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Jochen Vorreiter 
Status Released

--- Page 2 ---
Technical Reference MICROSAR EcuM Flex 
2015, Vector Informatik GmbH Version: 5.00.00 
based on template version 4.8.3 
2 / 134 
Document Information 
History 
Author Date Version Remarks 
Jochen Vorreiter 2012-06-06 1.00.00 > Initial Setup 
Jochen Vorreiter 2013-01-30 1.00.01 > ESCAN00064669 Updated compiler 
abstraction and memory mapping 
Jochen Vorreiter 2013-05-03 1.01.00 > Added support of post-build-loadable 
> Added support of asynchronous 
transceiver handling in 3.9.2 
> Added API 
EcuM_ClearValidatedWakeupEvent() 
in 5.2.10 
> Extended description of 
EcuM_StartupTwo() in 5.2.3 
Jochen Vorreiter 2013-10-31 2.00.00 > ESCAN00069010 Added support for 
Alarm Clock in 3.14 
> ESCAN00071546 Added Multi Core 
support in 3.15 
> New API 
EcuM_GoToSelectedShutdownTarget 
> ESCAN00071553 Changed handling of 
wakeup source states in 5.1 
> Changes in chapter 4.2 Critical Sections 
> ESCAN00071552 Removed 
BswM_EcuM_CurentState notification 
Jochen Vorreiter 2014-06-03 3.00.00 > Added Support for EcuM fixed 
> ESCAN00073631 Fixed missing 
description of EcuM_BswErrorHook() 
Jochen Vorreiter 2014-11-04 4.00.00 > Added Support for Post-Build 
Selectable 
> Added chapter 3.15.1.2.1 Driver 
initialization on the Slave Core. 
> Added chapter 3.15.5 Reconfiguration 
of the BSW Core ID 
> Added MICROSAR specific CanSM 
handling in 3.18.2.3.3 
> ESCAN00079382 Fixed missing 
description of the StateRequest Port in 
5.8.1.1 
> ESCAN00077124 Fixed description of 
Critical Sections in 4.2 
> ESCAN00079407, ESCAN00068331 
Fixed description in Type Definitions of

--- Page 3 ---
Technical Reference MICROSAR EcuM Flex 
2015, Vector Informatik GmbH Version: 5.00.00 
based on template version 4.8.3 
3 / 134 
EcuM_WakeupStateType in 5.1 
Jochen Vorreiter 2014-11-25 4.00.01 > Adapted description of 
EcuM_DeterminePbConfiguration 
Jochen Vorreiter 2015-01-26 4.01.00 > Updated the Include structure and 
added two files in 4.1.2 
> Updated access on PB and Variant data 
in DriverInitLists in Ch. 5.7.2 
Jochen Vorreiter 2015-07-14 5.00.00 > Added new EcuM error ID for invalid 
CoreID in Ch. 3.11.3 
> Added support for Mode Handling, see 
Ch. 3.16, 5.3.13 and 5.5 
> Removed subchapters “Parameter 
Checking” from Ch. 3.11 
> Added missing API ID in Table 3-8 
 Service IDs 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_SWS_ECUStateManager.pdf V3.0.0 
[2]  AUTOSAR AUTOSAR_SWS_DevelopmentErrorTracer.pdf V3.2.0 
[3]  AUTOSAR AUTOSAR_SWS_DiagnosticEventManager.pdf.pdf V4.2.0 
[4]  AUTOSAR AUTOSAR_TR_BSWModuleList.pdf V1.6.0 
[5]  AUTOSAR AUTOSAR_EXP_ModemanagementGuide.pdf V1.0.0 
[6]  VECTOR TechnicalReference_PostBuildLoadable.pdf see delivery 
[7]  AUTOSAR AUTOSAR_SWS_ECUStateManagerFixed.pdf V1.4.0 
[8]  VECTOR TechnicalReference_IdentityManager.pdf see delivery 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
Technical Reference MICROSAR EcuM Flex 
2015, Vector Informatik GmbH Version: 5.00.00 
based on template version 4.8.3 
4 / 134 
Contents 
1 Component History ................................ ................................ ................................ .... 13 
2 Introduction................................ ................................ ................................ ................. 14 
2.1 Architecture Overview ................................ ................................ ...................... 15 
3 Functional Description ................................ ................................ ...............................  17 
3.1 Features ................................ ................................ ................................ .......... 17 
3.2 States of EcuM flex ................................ ................................ .......................... 19 
3.3 States of EcuM fixed ................................ ................................ ........................ 20 
3.4 The State Diagram of the EcuM flex................................ ................................ . 22 
3.5 The State Diagram of the EcuM with fixed state machine ................................  23 
3.6 Initialization ................................ ................................ ................................ ...... 24 
3.6.1 EcuM_Init ................................ ................................ ......................... 24 
3.6.2 EcuM_StartupTwo ................................ ................................ ............ 24 
3.6.2.1 EcuM_StartupTwo in case of EcuM flex ......................... 24 
3.6.2.2 EcuM_StartupTwo in case of EcuM fixed ....................... 24 
3.6.3 Initialization Order ................................ ................................ ............ 24 
3.6.4 Additional Code in the Initialization Callouts ................................ ..... 25 
3.6.5 Inclusion of Additional Header Files ................................ ................. 26 
3.6.6 Configuration Set Selection ................................ ..............................  26 
3.7 Initialization of a MultiCore ECU ................................ ................................ ....... 27 
3.8 Shutdown Targets ................................ ................................ ............................ 27 
3.8.1 Using the API EcuM_SelectShutdownTarget()................................ .. 27 
3.8.2 Default Shutdown Target ................................ ................................ .. 27 
3.8.3 Reset Modes ................................ ................................ .................... 27 
3.8.4 Sleep Modes ................................ ................................ .................... 28 
3.9 Wake-up Sources ................................ ................................ ............................ 28 
3.9.1 Validation Timeout ................................ ................................ ............ 28 
3.9.2 Check-Wakeup Validation Timeout ................................ ................... 29 
3.9.3 ComM Channel Reference ................................ ...............................  29 
3.9.4 Polling of Wake-up Sources ................................ ............................. 29 
3.9.5 MCU Reset Reason ................................ ................................ ......... 29 
3.10 Main Functions ................................ ................................ ................................  30 
3.10.1 Wake-up Validation Protocol ................................ ............................ 30 
3.10.2 Wake-up Validation Protocol for asynchronous Can transceiver ....... 32 
3.11 Error Handling ................................ ................................ ................................ .. 33 
3.11.1 Development Error Reporting ................................ ........................... 33 
3.11.2 Production Code Error Reporting ................................ ..

--- Page 5 ---
Technical Reference MICROSAR EcuM Flex 
2015, Vector Informatik GmbH Version: 5.00.00 
based on template version 4.8.3 
5 / 134 
3.11.3 EcuM_ErrorHook ................................ ................................ ............. 35 
3.12 Callout Execution Sequences ................................ ................................ .......... 36 
3.12.1 Callouts from Startup to Run ................................ ............................ 36 
3.12.2 Callouts from Run to Sleep (Halt) and back to Run .......................... 37 
3.12.3 Callouts from Run to Reset ................................ ..............................  38 
3.12.4 Callouts from Run to Off ................................ ................................ ... 38 
3.13 EcuM Flex Users and Defensive Behavior ................................ ....................... 39 
3.14 Alarm Clock ................................ ................................ ................................ ..... 40 
3.14.1 Configuring the Gpt to provide the Time base ................................ .. 40 
3.14.2 Configuring the EcuM for using the Alarm Clock ..............................  40 
3.14.3 Setting of the EcuM Clock ................................ ................................  41 
3.14.4 Setting of a Time Triggered Wake Up Alarm ................................ ..... 41 
3.15 MultiCore Ecu ................................ ................................ ................................ .. 42 
3.15.1 Initialization of a MultiCore ECU ................................ ....................... 42 
3.15.1.1 Initialization on the Maste

[… 128 further page(s) not extracted …]
