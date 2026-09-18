---
title: "Diagnostic Event Manager — TechnicalReference Dem"
description: "Converted Technical Reference (vendor) from TechnicalReference_Dem.pdf (PDF, 2032 KB)."
---

:::note
Converted from `Dem/doc/TechnicalReference_Dem.pdf` (Technical Reference (vendor); original PDF, about 2032 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Dem](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR Diagnostic Event Manager 
(Dem) 
Technical Reference 
 
  
Version 4.3.0 
 
 
 
 
 
 
 
 
 
 
 
Authors Thomas Dedler, Alexander Ditte, Matthias Heil 
Status Released

--- Page 2 ---
Technical Reference MICROSAR Diagnostic Event Manager (Dem) 
2015, Vector Informatik GmbH Version: 4.3.0 
based on template version 5.0.0 
2 / 175 
Document Information 
History 
Author Date Version Remarks 
A. Ditte 2012-05-04 1.0.0 > Initial Version 
A. Ditte 2012-10-09 1.0.1 > Add chapter 6.2.4.18 and 6.6.1.2.11 
> Add GetEventEnableCondition to chapter 6.6.1.1.2 
M. Heil 2012-11-02 1.1.0 > Architecture Update 
A. Ditte,  
M. Heil 
2013-02-15 1.2.0 > Introduced Measurement and Calibration (chapter 5) 
> Extended chapters 3.3, 3.5, 3.15, 4.3 and 4.3.1 
> Added User Controlled WarningIndicatorRequest 
(chapter 3.16.1) 
> Added chapters 6.2.4.22, 6.2.4.23, 6.6.1.1.9 
M. Heil 2013-04-05 1.3.0 > Support for feature ‘DTC suppression’ 
> Added chapter 3.9, APIs 6.2.4.24, 6.2.4.25 
> Reworked table layout in chapters 4.3, 5.2 
> Reworked Measurement and Calibration (chapter 5) 
> Added measurable items (chapter 5.1)  
M. Heil 2013-06-17 1.4.0 > Added combined events 
> Reworked suppression 
T. Dedler 2013-07-22 1.4.1 > critical section description extended 
T. Dedler,  
M. Heil 
2013-09-04 2.0.0 > Service ID definition changed 
> Post-Build Loadable 
A. Ditte 2013-11-05 2.1.0 > Added OBD DTC and Root cause EventId to chapter 
3.10.2 
> Added limitation for internal data elements in chapter 
8.3 
A. Ditte, 
M. Heil 
2014-01-14 3.0.0 > Added J1939 (chapters 3.19, 6.2.7) 
> Adapted DCM interfaces (chapter 6.2.6) according 
AUTOSAR 4.1.2 
> Added chapter 4.3.1 
> Fixed ESCAN00071673: NVM configuration is not 
described 
> Fixed ESCAN00071511: Missing hint for supported 
feature 'individual post-build loadable' 
> Fixed ESCAN00073677: Incorrect figure for DEM 
initialization states

--- Page 3 ---
Technical Reference MICROSAR Diagnostic Event Manager (Dem) 
2015, Vector Informatik GmbH Version: 4.3.0 
based on template version 5.0.0 
3 / 175 
M. Heil 2014-03-27 3.1.0 > Describe deviation in handling operation cycles before 
module initialization. 
> Add dependency to configuration to Dcm APIs. 
> Added warning about time-based de-bouncing and 
maximum fault detection counter in current cycle 
M. Heil 2014-05-08 3.2.0 > Added Event Availability (chapters 3.9.1, 6.2.4.26) 
> Added freeze frame pre-storage (chapters 3.11, 6.2.4.4, 
6.2.4.5) 
> Corrected description of Event and DTC suppression 
(chapters 3.9, 6.2.4.4, 6.2.4.5) 
> Introduced chapter 3.3.3.4 
> Clarified usage of DTC groups (chapter 8.3) 
M. Heil 
A. Ditte 
2014-10-14 4.0.0 > Moved Initialization Pointer (see Dem_PreInit(), 
Dem_Init()) 
> Added API Dem_RequestNvSynchronization() 
> Added de-bounce values in NVRAM and  API 
Dem_NvM_InitDebounceData() 
> Added additional aging variant (chapter 3.5), added 
Figure 3-3 
> Added missing configuration variants (chapter 2, 
ESCAN00076237) 
> Added description for NVRAM write frequency (chapter 
3.13.2, ESCAN00078587) 
> Added description for NVRAM recovery (chapter 3.13.3, 
ESCAN00078582) 
> Added support of J1939 nodes 
M. Heil 2015-02-27 4.1.0 > Added APIs, chapters 6.2.4.3, 6.2.4.20 
> Support EnableCondition notification, 3.15.4 
> Added explanation of Dem task mapping, chapter 4.9 
> Added not of reduced queue depth for some events, 
chapter 3.3.3.2 
> Updated critical sections, chapter 4.4 
M. Heil 2015-04-20 4.1.1 > Added deviation regarding notification signatures 
(chapters 6.5.1, 8.1) 
> Reworked chapter 3.1 according ESCAN00082555  
M. Heil 2015-06-17 4.2.0 > Extended data callback support (chapters 3.10.3, 
6.5.1.6) 
> Described FDC statistics for DTCs using internal de-
bouncing (chapter 3.10.2) 
> Described aging target 0 (chapter 3.5.1) 
> Described effect of asynchronous behavior of $85 
(chapter 3.7) 
> Described different aging behavior (chapter 3.5.5)

--- Page 4 ---
Technical Reference MICROSAR Diagnostic Event Manager (Dem) 
2015, Vector Informatik GmbH Version: 4.3.0 
based on template version 5.0.0 
4 / 175 
M. Heil 2015-09-14 4.3.0 > More information about NVRam setup (chapter 4.5 ff) 
> Changes due to new option to persist event availability 
(chapters 3.9.1, 6.2.4.26, 6.2.4.11)

--- Page 5 ---
Technical Reference MICROSAR Diagnostic Event Manager (Dem) 
2015, Vector Informatik GmbH Version: 4.3.0 
based on template version 5.0.0 
5 / 175 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_SWS_DiagnosticEventManager.pdf V4.2.0, 
V5.1.0 
[2]  AUTOSAR AUTOSAR_SWS_DevelopmentErrorTracer.pdf V3.2.0 
[3]  AUTOSAR AUTOSAR_SWS_DiagnosticCommunicationManager.pdf V4.2.0 
[4]  AUTOSAR AUTOSAR_SWS_NVRAMManager.pdf V3.2.0 
[5]  AUTOSAR AUTOSAR_SWS_StandardTypes.pdf V1.3.0 
[6]  AUTOSAR AUTOSAR_TR_BSWModuleList.pdf V1.6.0 
[7]  ISO 14229-1 Road vehicles – Unified diagnostic services (UDS) 
– Part 1: Specification and requirements 
- 
[8]  Vector TechnicalReference_PostBuildLoadable.pdf See delivery 
[9]  Vector TechnicalReference_IdentityManager.pdf See delivery 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 6 ---
Technical Reference MICROSAR Diagnostic Event Manager (Dem) 
2015, Vector Informatik GmbH Version: 4.3.0 
based on template version 5.0.0 
6 / 175 
Contents 
1 Component History ................................ ................................ ................................ .... 16 
2 Introduction................................ ................................ ................................ ................. 17 
2.1 How to Read this Document ................................ ................................ ............ 17 
2.1.1 API Definitions ................................ ................................ ................. 17 
2.1.2 Configuration References ................................ ................................  18 
2.2 Architecture Overview ................................ ................................ ...................... 18 
3 Functional Description ................................ ................................ ...............................  20 
3.1 Features ................................ ................................ ................................ .......... 20 
3.2 Initialization ................................ ................................ ................................ ...... 22 
3.2.1 Initialization States ................................ ................................ ........... 23 
3.3 Diagnostic Event Processing ................................ ................................ ........... 24 
3.3.1 Event De-bouncing ................................ ................................ .......... 24 
3.3.1.1 Counter Based Algorithm ................................ ............... 24 
3.3.1.2 Time Based Algorithm ................................ .................... 25 
3.3.1.3 Monitor internal de-bouncing ................................ .......... 26 
3.3.2 Event Reporting ................................ ................................ ............... 27 
3.3.3 Event Status ................................ ................................ .................... 27 
3.3.3.1 Synchronous Status Bit Transitions ................................  28 
3.3.3.2 Asynchronous Status Bit Transitions ..............................  29 
3.3.3.3 Event Storage modifying Status Bits ..............................  29 
3.3.3.4 Lightweight Multiple Trips 
(FailureCycleCounterThreshold) ................................ .... 30 
3.4 Event Displacement ................................ ................................ ......................... 30 
3.5 Event Aging ................................ ................................ ................................ ...... 31 
3.5.1 Aging Target ‘0’ ................................ ................................ ................ 32 
3.5.2 Aging Counter Reallocation ................................ ..............................  32 
3.5.3 Aging of Environmental Data ................................ ............................ 33 
3.5.4 Aging of TestFailedSinceLastClear ................................ ................... 33 
3.5.5 Aging and Healing ................................ ................................ ............ 33 
3.6 Operation Cycles ................................ ................................ ............................. 34 
3.6.1 Persistent Storage of Operation Cycle State ................................ .... 34 
3.6.2 Automatic Operation Cycle Restart ................................ .................. 34 
3.7 Enable Conditions and Control DTC Setting ...............

[… 169 further page(s) not extracted …]
