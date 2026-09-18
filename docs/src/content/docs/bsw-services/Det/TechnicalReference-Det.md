---
title: "Development Error Tracer — TechnicalReference Det"
description: "Converted Technical Reference (vendor) from TechnicalReference_Det.pdf (PDF, 806 KB)."
---

:::note
Converted from `Det/doc/TechnicalReference_Det.pdf` (Technical Reference (vendor); original PDF, about 806 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Det](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR DET 
Technical Reference 
 
 
 
 
Version 2.4.0 
 
 
 
 
 
 
 
 
Authors Hartmut Hörner 
Version: 2.4.0 
Status: Released

--- Page 2 ---
Technical Reference MICROSAR DET  
2015, Vector Informatik GmbH Version: 2.4.0 
based on template version 2.0 
2 / 30 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Hartmut Hörner 2007-11-29 1.0 Initial version 
Hartmut Hörner 2008-01-03 1.1 Update to AUTOSAR 3 
Hartmut Hörner 2008-04-14 1.2 Naming changed to 
AUTOSAR short name, 
screen shots updated. 
(ESCAN00025687) 
Hartmut Hörner 2008-09-16 1.3 Added DET extension 
mechanism based on callout 
(4.7, 6.3.1). 
Added chapter 5.3. 
Hartmut Hörner 2010-01-13 2.0 Update to AUTOSAR 4 
Hartmut Hörner 2012-04-20 2.1 Added usage hints related to 
silent BSW concept in 5.4 
(ESCAN00058419) 
Hartmut Hörner 2013-04-09 2.2 Added Configurator 5 and 
service port interface 
(ESCAN00066511) 
Hartmut Hörner 2013-09-13 2.3 Added DLT forwarding 
support for Configurator 5 
(ESCAN00068394, 
ESCAN00069807) 
Hartmut Hörner 2014-12-10 2.3.1 Added description of  
BCD-coded return value of 
Det_GetVersionInfo() 
(ESCAN00079310) 
Hartmut Hörner 2015-06-12 2.4.0 File name changed 
(ESCAN00081049) 
Added chapter 5.4. 
Table 1-1  History of the Document

--- Page 3 ---
Technical Reference MICROSAR DET  
2015, Vector Informatik GmbH Version: 2.4.0 
based on template version 2.0 
3 / 30 
1.2 Reference Documents 
Index Document 
[1] AUTOSAR_SWS_DET.pdf, Version 2.2.0 
[2] AUTOSAR_SWS_DET.pdf, Version 3.0.0 
  
Table 1-2  Referenced documents 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
Technical Reference MICROSAR DET  
2015, Vector Informatik GmbH Version: 2.4.0 
based on template version 2.0 
4 / 30 
Contents 
1 Document Information ................................ ................................ ................................ . 2 
1.1 History ................................ ................................ ................................ ............... 2 
1.2 Reference Documents ................................ ................................ ....................... 3 
2 Component History ................................ ................................ ................................ ...... 7 
3 Introduction................................ ................................ ................................ ................... 8 
3.1 Architecture Overview ................................ ................................ ........................ 8 
4 Functional Description ................................ ................................ ...............................  10 
4.1 Features ................................ ................................ ................................ .......... 10 
4.2 Initialization ................................ ................................ ................................ ...... 10 
4.3 States ................................ ................................ ................................ .............. 10 
4.4 Main Functions ................................ ................................ ................................  11 
4.5 Error Handling ................................ ................................ ................................ .. 11 
4.6 Debugging with the DET ................................ ................................ .................. 11 
4.6.1 Extended Debug Features ................................ ...............................  11 
4.6.1.1 Filters ................................ ................................ ............. 11 
4.6.1.2 Logging ................................ ................................ .......... 12 
4.6.1.3 Break handler ................................ ................................  13 
4.7 Extension of the DET ................................ ................................ ....................... 15 
5 Integration ................................ ................................ ................................ ................... 16 
5.1 Scope of Delivery ................................ ................................ ............................. 16 
5.1.1 Static Files ................................ ................................ ....................... 16 
5.1.2 Generated Files ................................ ................................ ............... 16 
5.2 Include Structure ................................ ................................ ..............................  16 
5.3 Handling of Recursions ................................ ................................ .................... 16 
5.4 Critical Sections ................................ ................................ ...............................  17 
5.5 Usage Hints for Operation in Safety Related ECUs ................................ .......... 17 
6 API Description ................................ ................................ ................................ ........... 18 
6.1 Interfaces Overview ................................ ................................ ......................... 18 
6.2 Services Provided by MICROSAR DET ................................ ........................... 18 
6.2.1 Det_Init ................................ ................................ ............................ 18 
6.2.2 Det_InitMemory ................................ ................................ ................ 19 
6.2.3 Det_Start ................................ ................................ .......................... 19 
6.2.4 Det_ReportError ................................ ...............................

--- Page 5 ---
Technical Reference MICROSAR DET  
2015, Vector Informatik GmbH Version: 2.4.0 
based on template version 2.0 
5 / 30 
6.3.1 Appl_DetEntryCallout ................................ ................................ ....... 22 
6.4 Callback Functions ................................ ................................ ........................... 22 
6.5 Configurable Interfaces ................................ ................................ .................... 23 
6.6 Service Ports ................................ ................................ ................................ ... 24 
6.6.1 Client Server Interface ................................ ................................ ..... 24 
6.6.1.1 Provide Ports on DET Side ................................ ............ 24 
6.6.1.1.1 DETService................................ ................ 24 
7 Configuration ................................ ................................ ................................ .............. 25 
7.1 Configuration with GENy ................................ ................................ .................. 25 
7.1.1 System Configuration ................................ ................................ ....... 25 
7.1.2 Component Configuration ................................ ................................  25 
8 AUTOSAR Standard Compliance................................ ................................ ............... 27 
8.1 Deviations ................................ ................................ ................................ ........ 27 
8.1.1 Support of Service Port Interface ................................ ..................... 27 
8.1.2 Support of AUTOSAR Debugging Concept (AUTOSAR 4) ............... 27 
8.1.3 Support of Configurable List of Error Hooks (AUTOSAR 4) .............. 27 
8.2 Additions/ Extensions ................................ ................................ ....................... 27 
8.2.1 Extended Debug Features ................................ ...............................  27 
8.2.2 DET Extension Mechanism ................................ ..............................  27 
8.3 Limitations................................ ................................ ................................ ........ 27 
9 Abbreviations ................................ ................................ ................................ .............. 28 
10 Glossary ................................ ................................ ................................ ...................... 29 
11 Contact ................................ ................................ ................................ ........................ 30

--- Page 6 ---
Technical Reference MICROSAR DET  
2015, Vector Informatik GmbH Version: 2.4.0 
based on template version 2.0 
6 / 30 
Illustrations 
Figure 3-1 AUTOSAR architecture ................................ ................................ ............... 8 
Figure 3-2 Interfaces to adjacent modules of the DET ................................ ...............

[… 24 further page(s) not extracted …]
