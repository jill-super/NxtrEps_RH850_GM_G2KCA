---
title: "Flash EEPROM Emulation — TechnicalReference Fee"
description: "Converted Technical Reference (vendor) from TechnicalReference_Fee.pdf (PDF, 1862 KB)."
---

:::note
Converted from `Fee/doc/TechnicalReference_Fee.pdf` (Technical Reference (vendor); original PDF, about 1862 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Fee](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR FEE 
Technical Reference 
 
  
Version 8.01.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Christian Kaiser 
Status Released

--- Page 2 ---
Technical Reference MICROSAR FEE   
2015, Vector Informatik GmbH Version: 8.01.00 
based on template version 3.1 
2 / 85 
Document Information 
History 
Author Date Version Remarks 
Christian Kaiser 2012-06-26 8.00.00 - Removed revision history entries, due to 
major changes in component. 
- Removed all references to Fee30Inst2 
- Added Ch. 2.4.2 “Partitions”, 
- Added Ch. 4.3.2 “Fee_InitEx”, updated Ch. 
4.3.1 
- Reworked Ch. 2.3, Ch. 2.6, Ch. 2.10, Ch. 
3.1.1, 4.4.1, Ch. 5  
- Changes throughout the document: 
introduction of partitions 
- Added Ch. 6.3.4 
- Added Ch. 2.4.3.1 
Christian Kaiser 2012-09-20 8.00.01 - Minor editorial changes in Ch. 5 
- Added Ch. 5.2.1 
Christian Kaiser 2013-03-05 8.00.02 - Ch. 1:  AUTOSAR version(s) 
- Ch. 6.3.1: maximum number of Partitions 
Christian Kaiser 2014-03-11 8.00.03 - Editorial changes (rework of review 
findings) 
- Ch. 5.1.5.5: corrected description of 
“Suspend Long” 
- Ch. 3.5: Critical Section description 
- Ch. 1.1 – updated figure, added notes. 
Claudia Mausz 2015-02-13 8.01.00 - Add new chapter: 
 2.12 Fee_MainFunction Triggering 
Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_Flash_EEPROM_Emulation.pdf -- 
[2] AUTOSAR_SWS_DET.pdf V2.2.1 
[3] AUTOSAR_BasicSoftwareModules.pdf V1.3.0 
 
  
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR FEE   
2015, Vector Informatik GmbH Version: 8.01.00 
based on template version 3.1 
3 / 85 
Contents 
1 Introduction................................ ................................ ................................ ................... 9 
1.1 Architecture Overview ................................ ................................ ...................... 10 
2 Functional Description ................................ ................................ ...............................  12 
2.1 Features ................................ ................................ ................................ .......... 12 
2.2 Initialization ................................ ................................ ................................ ...... 13 
2.3 States ................................ ................................ ................................ .............. 13 
2.3.1 Module States ................................ ................................ .................. 13 
2.3.2 Job States/Results ................................ ................................ ........... 16 
2.4 Flash organization ................................ ................................ ............................ 17 
2.4.1 Block Handling ................................ ................................ ................. 17 
2.4.1.1 Block Chunks ................................ ................................ . 17 
2.4.1.2 Block Search................................ ................................ .. 18 
2.4.2 Partitions ................................ ................................ .......................... 18 
2.4.3 Logical Sectors ................................ ................................ ................ 19 
2.5 Processing ................................ ................................ ................................ ....... 20 
2.5.1.1 Initial processing ................................ ............................ 20 
2.5.1.2 Processing of Read Job ................................ ................. 21 
2.5.1.3 Processing of Write Job ................................ ................. 21 
2.5.1.4 Processing of InvalidateBlock Job ................................ .. 21 
2.5.1.5 Processing of EraseImmediateBlock Job ....................... 22 
2.5.1.6 Processing of GetEraseCycle Job ................................ .. 22 
2.5.1.7 Processing of GetWriteCycle Job ................................ ... 22 
2.6 Error Handling ................................ ................................ ................................ .. 22 
2.6.1 Development Error Reporting ................................ ........................... 23 
2.6.1.1 Parameter Checking ................................ ...................... 24 
2.6.2 Production Code Error Reporting ................................ ..................... 25 
2.6.3 Error notification ................................ ................................ ............... 25 
2.7 Sector Switch ................................ ................................ ................................ ... 26 
2.7.1 Background Sector Switch (BSS) ................................ ..................... 26 
2.7.2 Foreground Sector Switch (FSS)................................ ...................... 26 
2.7.3 Sector Overflow ................................ ................................ ............... 27 
2.7.4 Sector switch reserves and thresholds ................................ ............. 27 
2.7.5 Background Sector Switch Reserve/Threshold ................................  28 
2.7.6 Foreground Sector Switch/Threshold ................................ ............... 29 
2.8 Data Conversion ................................ ................................ ..............................  29 
2.9 Flash Page Size impacts ................................ ................................ .................. 30 
2.10 Services for handling under-voltage situations .......................

--- Page 4 ---
Technical Reference MICROSAR FEE   
2015, Vector Informatik GmbH Version: 8.01.00 
based on template version 3.1 
4 / 85 
2.11 Critical Data Blocks ................................ ................................ .......................... 32 
2.12 Fee_MainFunction Triggering ................................ ................................ .......... 33 
3 Integration ................................ ................................ ................................ ................... 34 
3.1 Scope of Delivery ................................ ................................ ............................. 34 
3.1.1 Static Files ................................ ................................ ....................... 34 
3.1.2 Dynamic Files ................................ ................................ .................. 34 
3.2 Compiler Abstraction and Memory Mapping ................................ ..................... 35 
3.3 Dependencies on SW Modules ................................ ................................ ........ 36 
3.3.1 OSEK/AUTOSAR OS ................................ ................................ ....... 36 
3.3.2 Module SchM ................................ ................................ ................... 37 
3.3.3 Module Det ................................ ................................ ...................... 37 
3.3.4 Module Fls ................................ ................................ ....................... 37 
3.3.5 Callback Functions ................................ ................................ ........... 38 
3.3.5.1 Lower layer interaction ................................ ................... 38 
3.3.5.2 Upper layer interaction ................................ ................... 38 
3.3.5.3 User Error Callback................................ ........................ 39 
3.4 Dependencies on HW modules ................................ ................................ ........ 40 
3.5 Critical Sections ................................ ................................ ...............................  40 
4 API Description ................................ ................................ ................................ ........... 41 
4.1 Interfaces Overview ................................ ................................ ......................... 41 
4.2 Type Definitions ................................ ................................ ...............................  41 
4.2.1 Fee_SectorSwitchStatusType ................................ .......................... 41 
4.2.2 Fee_SectorErrorType ................................ ................................ ....... 41 
4.3 Services provided by FEE ................................ ................................ ................ 42 
4.3.1 Fee_Init ................................ ................................ ............................ 42 
4.3.2 Fee_InitEx ................................ ................................ ........................ 43 
4.3.3 Fee_SetMode ................................ ................................ .................. 44 
4.3.4 Fee_Read ................................ ......................

[… 79 further page(s) not extracted …]
