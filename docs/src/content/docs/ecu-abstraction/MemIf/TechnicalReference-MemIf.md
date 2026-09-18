---
title: "Memory Abstraction Interface — TechnicalReference MemIf"
description: "Converted Technical Reference (vendor) from TechnicalReference_MemIf.pdf (PDF, 730 KB)."
---

:::note
Converted from `MemIf/doc/TechnicalReference_MemIf.pdf` (Technical Reference (vendor); original PDF, about 730 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to MemIf](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR MemIf 
Technical Reference 
 
  
Version 2.02.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Tobias Schmid, Manfred Duschinger, Michael Goß 
Status Released

--- Page 2 ---
Technical Reference MICROSAR MemIf   
2015, Vector Informatik GmbH Version: 2.02.00 
based on template version 3.1 
2 / 25 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Tobias Schmid 2008-04-14 1.0 Creation of document 
Manfred Duschinger 2013-02-20 1.01.00 Ch. 4.1. Update files 
according to new generator 
Ch. 6 Update Configuration 
Michael Goß 2014-11-21 2.01.01 Typos were corrected and 
content was modified a little  
Michael Goß 2015-04-23 2.02.00 Content was updated 
regarding SafeBSW MemIf 
Table 1-1  History of the document 
1.2 Reference Documents 
No. Title Version 
[1]  AUTOSAR_SWS_Mem_AbstractionInterface.pdf V1.4.0 
[2]  AUTOSAR_SWS_DET.pdf V2.2.0 
[3]  AUTOSAR_BasicSoftwareModules.pdf V1.0.0 
[4]  AUTOSAR_SWS_EEPROM_Abstraction.pdf V2.0.0 
[5]  AUTOSAR_SWS_Flash_EEPROM_Emulation.pdf V2.0.0 
Table 1-2  Reference documents 
 
1.3 Scope of the Document 
This technical reference describes the general use of module MemIf (AUTOSAR Memory 
Abstraction Interface). 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR MemIf   
2015, Vector Informatik GmbH Version: 2.02.00 
based on template version 3.1 
3 / 25 
Contents 
1 Document Information ................................ ................................ ................................ . 2 
1.1 History ................................ ................................ ................................ ............... 2 
1.2 Reference Documents ................................ ................................ ....................... 2 
1.3 Scope of the Document................................ ................................ ...................... 2 
2 Introduction................................ ................................ ................................ ................... 6 
2.1 Architecture Overview ................................ ................................ ........................ 7 
3 Functional Description ................................ ................................ ................................ . 8 
3.1 Features ................................ ................................ ................................ ............ 8 
3.2 Initialization ................................ ................................ ................................ ........ 8 
3.3 Main Functions ................................ ................................ ................................ .. 8 
3.4 Error Handling ................................ ................................ ................................ .... 8 
3.4.1 Development Error Reporting ................................ ............................. 8 
3.4.1.1 Parameter Checking ................................ ........................ 9 
4 Integration ................................ ................................ ................................ ................... 11 
4.1 Scope of Delivery ................................ ................................ ............................. 11 
4.1.1 Static Files ................................ ................................ ....................... 11 
4.1.2 Dynamic Files ................................ ................................ .................. 11 
4.2 Include Structure ................................ ................................ ..............................  12 
4.3 Compiler Abstraction and Memory Mapping ................................ ..................... 12 
5 API Description ................................ ................................ ................................ ........... 14 
5.1 Interfaces Overview ................................ ................................ ......................... 14 
5.2 Type Definitions ................................ ................................ ...............................  14 
5.3 Services provided by MemIf ................................ ................................ ............. 15 
5.3.1 MemIf_GetVersionInfo ................................ ................................ ..... 15 
5.3.2 MemIf_SetMode ................................ ................................ ............... 16 
5.3.3 MemIf_Read ................................ ................................ .................... 16 
5.3.4 MemIf_Write ................................ ................................ ..................... 17 
5.3.5 MemIf_Cancel ................................ ................................ .................. 18 
5.3.6 MemIf_GetStatus ................................ ................................ ............. 18 
5.3.7 MemIf_GetJobResult ................................ ................................ ....... 19 
5.3.8 MemIf_EraseImmediateBlock ................................ .......................... 20 
5.3.9 MemIf_InvalidateBlock ................................ ................................ ..... 20 
5.4 Services used by MemIf ................................ ................................ ................... 21 
6 Configuration ................

--- Page 4 ---
Technical Reference MICROSAR MemIf   
2015, Vector Informatik GmbH Version: 2.02.00 
based on template version 3.1 
4 / 25 
7 AUTOSAR Standard Compliance................................ ................................ ............... 23 
7.1 Deviations ................................ ................................ ................................ ........ 23 
7.1.1 Extension of Error Codes ................................ ................................ . 23 
7.2 Additions/ Extensions ................................ ................................ ....................... 23 
8 Glossary and Abbreviations ................................ ................................ ...................... 24 
8.1 Glossary ................................ ................................ ................................ .......... 24 
8.2 Abbreviations ................................ ................................ ................................ ... 24 
9 Contact ................................ ................................ ................................ ........................ 25

--- Page 5 ---
Technical Reference MICROSAR MemIf   
2015, Vector Informatik GmbH Version: 2.02.00 
based on template version 3.1 
5 / 25 
Illustrations 
Figure 2-1 AUTOSAR architecture ................................ ................................ ............... 7 
Figure 2-2 Interfaces to adjacent modules of the MemIf................................ ............... 7 
Figure 4-1 Include structure ................................ ................................ ....................... 12 
Figure 5-1 MemIf interactions with other BSW ................................ ........................... 14 
 
Tables 
Table 1-1  History of the document ................................ ................................ .............. 2 
Table 1-2  Reference documents ................................ ................................ ................. 2 
Table 3-1  Supported SWS features ................................ ................................ ............ 8 
Table 3-2  Mapping of service IDs to services ................................ ............................. 9 
Table 3-3  Errors reported to DET ................................ ................................ ............... 9 
Table 3-4  Development Error Reporting: Assignment of checks to services ............... 9 
Table 4-1  Static files ................................ ................................ ................................ . 11 
Table 4-2  Generated files ................................ ................................ ......................... 11 
Table 4-3  Compiler abstraction and memory mapping ................................ .............. 13 
Table 5-1  Type definitions ................................ ................................ ......................... 15 
Table 5-2  MemIf_GetVersionInfo ................................ ................................ .............. 16 
Table 5-3  MemIf_SetMode ................................ ................................ ....................... 16 
Table 5-4  MemIf_Read ................................ ................................ ............................. 17 
Table 5-5  MemIf_Write ................................ ................................ ............................. 18 
Table 5-6  MemIf_Cancel ................................ .

[… 19 further page(s) not extracted …]
