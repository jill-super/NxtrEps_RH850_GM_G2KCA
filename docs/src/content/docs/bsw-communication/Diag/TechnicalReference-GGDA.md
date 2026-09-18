---
title: "Diagnostic Gateway Addon — TechnicalReference GGDA"
description: "Converted Technical Reference (vendor) from TechnicalReference_GGDA.pdf (PDF, 737 KB)."
---

:::note
Converted from `Diag/doc/TechnicalReference_GGDA.pdf` (Technical Reference (vendor); original PDF, about 737 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Diag](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
1 / 41 
 
 
 
 
 
 
 
 
 
 
 
GM Gateway Diagnostic Add-On 
Technical Reference 
 
GGDA 
Version 1.8 
 
 
 
 
 
 
 
 
 
 
Authors Mishel Shishmanyan, Matthias Heil 
Status Released

--- Page 2 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
2 / 41 
Document Information 
History 
Author Date Version Remarks 
Mishel Shishmanyan 2005-11-08 1.0 Created 
Mishel Shishmanyan 2006-01-31 1.1 Rework and textual corrections. 
Matthias Heil 2006-02-20 1.2 Extensions for multibus support 
Mishel Shishmanyan 2007-01-24 1.3 Modified:  
- 5.1.1 “1st step – GENtool” 
- 5.1.1.2 ”UUDT Transmitter 
Configuration” 
- 5.1.2 “2nd step – Ggda_par.h 
file” 
 
Added: 
- 5.2 “Timings Parameter” 
- 5.3 “Supported Diagnostic 
Services” 
- 5.4 “Development and 
Integration Support” 
- 5.5 “Target Address Acceptance 
on Functional Requests” 
Mishel Shishmanyan 2007-02-16 1.4 Modified: 
- 5.1.3.1”CAN Channel 
Configuration” 
Added: 
- 5.3.1 
InitializeDiagnosticOperationMode 
($10 $xx) 
- 5.3.3 ReadDiagnosticInformation 
($A5 $02) 
Matthias Heil 2007-05-29 1.5 Added: Infobox clarifying cdb-
Attributes for functional receive 
message 
Matthias Heil 2008-04-04 1.6 Added: Configuration aspects 
regarding GENy configuration Tool 
Matthias Heil 2012-05-04 1.7 Added: Added description of 
configuration file values for mode 
$A9 selection 
Matthias Heil 2015-05-28 1.8 Added: Precondition for 
DisableNormalCommunication 
(Sid: $28)

--- Page 3 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
3 / 41 
Reference Documents 
No. Title 
[1] TechnicalReference_CANdesc_GM_Opel.pdf 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
4 / 41 
Contents 
1 Introduction................................ ................................ ................................ ................... 7 
2 Overview ................................ ................................ ................................ ....................... 8 
3 Management Functions ................................ ................................ ................................  9 
3.1 Initialization ................................ ................................ ................................ ........ 9 
3.2 Processing ................................ ................................ ................................ ......... 9 
4 What is inside ................................ ................................ ................................ ............. 11 
4.1 InitializeDiagnosticOperationMode (Sid $10) ................................ .................... 11 
4.1.1 DisableAllDTCs ( $02) ................................ ................................ ...... 11 
4.1.2 WakeUp Link ($04) ................................ ................................ .......... 12 
4.2 ReadEcuIdentification (Sid $1A) ................................ ................................ ...... 13 
4.3 ReturnToNormalMode (Sid: $20) ................................ ................................ ...... 14 
4.4 DisableNormalCommunication (Sid: $28) ................................ ........................ 15 
4.5 TesterPresent (Sid $3E) ................................ ................................ ................... 17 
4.6 ProgrammingMode (Sid: $A5) ................................ ................................ .......... 18 
4.6.1 RequestProgrammingMode ($01) ................................ .................... 18 
4.6.2 RequestHiSpeedProgrammingMode ($02) ................................ ....... 19 
4.6.3 EnableProgrammingMode ($03) ................................ ...................... 20 
4.7 ReadDiagnosticInformation (Sid: $A9) ................................ ............................. 21 
4.7.1 ReadStatusOfDTCByDTCNumber ($80) ................................ .......... 21 
4.7.2 ReadStatusOfDTCByStatusMask ($81) ................................ ........... 23 
4.7.3 SendOnChangeDTCCount ($82) ................................ ..................... 26 
5 Configuration in CANGen ................................ ................................ .......................... 28 
5.1 Communication Parameter ................................ ................................ .............. 28 
5.1.1 1st step – GENtool ................................ ................................ ............ 28 
5.1.1.1 USDT Connection Configuration ................................ .... 29 
5.1.1.2 UUDT Transmitter Configuration ................................ .... 31 
5.1.2 2nd step – Ggda_par.h file ................................ ................................ . 32 
5.1.3 3rd step – Ggda_par.c file ................................ ................................ . 32 
5.1.3.1 CAN Channel Configuration ................................ ........... 32 
5.1.3.2 Static TP Channel Configuration ................................ .... 33 
5.2 Timings Parameter ................................ ................................ ........................... 34 
5.3 Supported Diagnostic Services ................................ ................................ ........ 36 
5.3.1 InitializeDiagnosticOperationMode ($10 $xx) ................................ ... 36 
5.3.2 ReadDiagnosticInformation ($A9) ................................ .................... 36 
5.3.3 ReadDiagnosticInformation ($A5 $02) ................................ ............. 36

--- Page 5 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
5 / 41 
5.4 Development and Integration Support ................................ ..............................  37 
5.5 Target Address Acceptance on Functional Requests ................................ ........ 37 
6 Configuration in GENy ................................ ................................ ...............................  38 
6.1 Communication Parameters ................................ ................................ ............. 38 
6.2 General Parameters ................................ ................................ ......................... 38 
6.3 Supported Diagnostic services ................................ ................................ ......... 39 
7 Integration ................................ ................................ ................................ ................... 40 
8 Contact ................................ ................................ ................................ ........................ 41

--- Page 6 ---
Technical Reference GM Gateway Diagnostic Add-On 
2015, Vector Informatik GmbH Version: 1.8 
based on template version 5.1.0 
6 / 41 
Figures 
Figure 2-1 System overview. ................................ ................................ ........................ 8 
Figure 5-1 GGDA OSEK-TP configuration ................................ ................................ . 29 
Figure 5-2 User-config file for the GGDA TPMC configuration. ................................ .. 30 
Figure 5-3 „GgdaFuncPrecopy“ configuration. ................................ ........................... 30 
Figure 5-4 „GgdaUudtConfirmation“ configuration................................ ...................... 31 
Figure 6-1 Global configuration parameters in GENy ................................ ................. 38 
Figure 6-2 Channel specific configuration parameters in GENy ................................ . 39 
 
Tables 
Table 3-1  GgdaTimerTask ................................ ................................ ........................ 10 
Table 3-2  GgdaStateTask ................................ ................................ ......................... 10 
Table 4-1  ApplGgdaOnDisableAllDtc ................................ ................................ ........ 11 
Table 4-2  ApplGgdaOnWakeUpLink ................................ ................................ ......... 12 
Table 4-3  ApplGgdaOnReturnToNormalMode ................................ .......................... 14 
Table 4-4  ApplGgdaForceEcuReset ................................ ................................ ......... 14 
Table 4-5  ApplGgdaMayDisableNormalComm ................................ ......................... 15 
Table 4-6  ApplGgdaOnDisableNormalComm ................................ ..............

[… 35 further page(s) not extracted …]
