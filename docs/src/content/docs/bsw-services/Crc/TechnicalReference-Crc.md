---
title: "Cyclic Redundancy Check Library — TechnicalReference Crc"
description: "Converted Technical Reference (vendor) from TechnicalReference_Crc.pdf (PDF, 629 KB)."
---

:::note
Converted from `Crc/doc/TechnicalReference_Crc.pdf` (Technical Reference (vendor); original PDF, about 629 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Crc](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR CRC 
Technical Reference 
 
  
Version 4.02.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Michael Goß 
Status Released

--- Page 2 ---
Technical Reference MICROSAR CRC 
2015, Vector Informatik GmbH Version: 4.02.00 
based on template version 5.9.0 
2 / 21 
Document Information 
History 
Author Date Version Remarks 
Tobias Schmid 2006-12-13 1.0 Initial Version 
Tobias Schmid 2008-01-21 3.00.00 Update to ASR 2.1 
Changed versioning to new notation 
Claudia Mausz 2008-05-19 4.00.00 Update to ASR 3 
Add Crc8 calculation 
Michael Goß 2014-11-18 4.01.00 Update to ASR 4 
Add Crc8H2F calculation 
Michael Goß 2015-05-08 4.02.00 SafeBSW 
Add Crc32P4 calculation 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_SWS_CRCLibrary.pdf V4.2.0 
[2]  AUTOSAR AUTOSAR_TR_BSWModuleList.pdf V1.6.0 
Scope of the Document  
This technical reference describes the general use of the CRC library  basis softwa re. 
There are no aspects which are controller specific. 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR CRC 
2015, Vector Informatik GmbH Version: 4.02.00 
based on template version 5.9.0 
3 / 21 
Contents 
1 Component History ................................ ................................ ................................ ...... 6 
2 Introduction................................ ................................ ................................ ................... 7 
2.1 Architecture Overview ................................ ................................ ........................ 8 
3 Functional Description ................................ ................................ ................................ . 9 
3.1 Features ................................ ................................ ................................ ............ 9 
3.1.1 Deviations ................................ ................................ .......................... 9 
3.1.2 Additions/ Extensions ................................ ................................ ....... 10 
3.2 Initialization ................................ ................................ ................................ ...... 10 
3.3 States ................................ ................................ ................................ .............. 10 
3.4 Main Functions ................................ ................................ ................................  10 
3.5 Error Handling ................................ ................................ ................................ .. 10 
3.5.1 Development Error Reporting ................................ ........................... 10 
3.5.2 Production Code Error Reporting ................................ ..................... 10 
3.5.3 Parameter Checking ................................ ................................ ........ 10 
4 Integration ................................ ................................ ................................ ................... 11 
4.1 Scope of Delivery ................................ ................................ ............................. 11 
4.1.1 Static Files ................................ ................................ ....................... 11 
4.1.2 Dynamic Files ................................ ................................ .................. 11 
4.2 Include Structure ................................ ................................ ..............................  11 
5 API Description ................................ ................................ ................................ ........... 12 
5.1 Type Definitions ................................ ................................ ...............................  12 
5.2 Interrupt Service Routines provided by CRC ................................ .................... 12 
5.3 Services provided by CRC ................................ ................................ ............... 12 
5.3.1 Crc_CalculateCRC8 ................................ ................................ ......... 12 
5.3.2 Crc_CalculateCRC8H2F ................................ ................................ .. 13 
5.3.3 Crc_CalculateCRC16 ................................ ................................ ....... 14 
5.3.4 Crc_CalculateCRC32 ................................ ................................ ....... 15 
5.3.5 Crc_CalculateCRC32P4 ................................ ................................ .. 17 
5.3.6 Crc_GetVersionInfo ................................ ................................ .......... 18 
5.4 Services used by CRC ................................ ................................ ..................... 18 
5.5 Callback Functions ................................ ................................ ........................... 18 
5.6 Configurable Interfaces ................................ ................................ .................... 18 
5.6.1 Notifications ................................ ................................ ..................... 18 
5.6.2 Callout Functions .........

--- Page 4 ---
Technical Reference MICROSAR CRC 
2015, Vector Informatik GmbH Version: 4.02.00 
based on template version 5.9.0 
4 / 21 
6 Configuration ................................ ................................ ................................ .............. 19 
6.1 Configuration Variants ................................ ................................ ...................... 19 
7 Glossary and Abbreviations ................................ ................................ ...................... 20 
7.1 Glossary ................................ ................................ ................................ .......... 20 
7.2 Abbreviations ................................ ................................ ................................ ... 20 
8 Contact ................................ ................................ ................................ ........................ 21

--- Page 5 ---
Technical Reference MICROSAR CRC 
2015, Vector Informatik GmbH Version: 4.02.00 
based on template version 5.9.0 
5 / 21 
Illustrations 
Figure 2-1 AUTOSAR 4.x Architecture Overview ................................ ......................... 8 
Figure 4-1 Include structure ................................ ................................ ....................... 11 
 
Tables 
Table 1-1  Component history................................ ................................ ...................... 6 
Table 3-1  Supported AUTOSAR standard conform features ................................ ....... 9 
Table 3-2  Not supported AUTOSAR standard conform features ................................ . 9 
Table 3-3  Features provided beyond the AUTOSAR standard ................................ .. 10 
Table 4-1  Static files ................................ ................................ ................................ . 11 
Table 4-2  Generated files ................................ ................................ ......................... 11 
Table 5-1  Type definitions ................................ ................................ ......................... 12 
Table 5-2  Std_VersionInfoType ................................ ................................ ................. 12 
Table 5-3  SAE-J1850 CRC8 Standard ................................ ................................ ..... 13 
Table 5-4  Crc_CalculateCRC8 ................................ ................................ ................. 13 
Table 5-5  CRC calculation based on 0x2F polynomial ................................ .............. 14 
Table 5-6  Crc_CalculateCRC8H2F ................................ ................................ ........... 14 
Table 5-7  CCITT CRC16 Standard ................................ ................................ ........... 15 
Table 5-8  Crc_CalculateCRC16 ................................ ................................ ............... 15 
Table 5-9  IEEE-802.3 CRC32 Ethernet Standard ................................ ..................... 16 
Table 5-10  Crc_CalculateCRC32 ................................ ................................ ............... 16 
Table 5-11  CRC32 calculation based on 0xF4ACFB13 polynomial (E2E Protection 
Profile 4) ................................ ................................ ................................ ... 17 
Table 5-12  Crc_CalculateCRC32P4 ................................ ................................ ........... 17 
Table 5-13  Crc_GetVersionInfo ................................ ................................ .................. 18 
Table 7-1  Glossary ................................ ................................ ....................

[… 15 further page(s) not extracted …]
