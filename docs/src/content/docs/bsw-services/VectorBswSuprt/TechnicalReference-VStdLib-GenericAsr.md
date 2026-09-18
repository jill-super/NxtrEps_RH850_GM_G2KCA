---
title: "Vector Basic Software Support Library — TechnicalReference VStdLib GenericAsr"
description: "Converted Technical Reference (vendor) from TechnicalReference_VStdLib_GenericAsr.pdf (PDF, 716 KB)."
---

:::note
Converted from `VectorBswSuprt/doc/02.00.00/TechnicalReference_VStdLib_GenericAsr.pdf` (Technical Reference (vendor); original PDF, about 716 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to VectorBswSuprt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR VStdLib 
Technical Reference 
 
Generic implementation of the Vector Standard Library 
Version 1.00.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Torsten Kercher 
Status Released

--- Page 2 ---
Technical Reference MICROSAR VStdLib 
2015, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.9.0 
2 / 26 
Document Information 
 
History 
Author Date Version Remarks 
Torsten Kercher 2015-05-04 1.00.00 Creation 
 
 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_TR_BSWModuleList.pdf 1.6.0 
[2]  AUTOSAR AUTOSAR_SWS_DevelopmentErrorTracer.pdf 3.2.0 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR VStdLib 
2015, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.9.0 
3 / 26 
Contents 
1 Component History ................................ ................................ ................................ ...... 5 
2 Introduction................................ ................................ ................................ ................... 6 
2.1 Architecture Overview ................................ ................................ ........................ 6 
3 Functional Description ................................ ................................ ................................ . 8 
3.1 Features ................................ ................................ ................................ ............ 8 
3.2 Initialization and Main Functions ................................ ................................ ........ 8 
3.3 Error Handling ................................ ................................ ................................ .... 8 
4 Integration ................................ ................................ ................................ ..................... 9 
4.1 Scope of Delivery ................................ ................................ ...............................  9 
4.2 Include Structure ................................ ................................ ................................  9 
4.3 Critical Sections ................................ ................................ ................................ . 9 
4.4 Compiler Abstraction and Memory Mapping ................................ ..................... 10 
4.5 Integration Hints ................................ ................................ ...............................  11 
5 API Description ................................ ................................ ................................ ........... 12 
5.1 Type Definitions ................................ ................................ ...............................  12 
5.2 Services provided by VStdLib ................................ ................................ .......... 12 
5.3 Services used by VStdLib ................................ ................................ ................ 22 
6 Configuration ................................ ................................ ................................ .............. 23 
6.1 Configuration Variants ................................ ................................ ...................... 23 
6.2 Manual Configuration in Header File ................................ ................................  23 
7 Abbreviations ................................ ................................ ................................ .............. 25 
8 Contact ................................ ................................ ................................ ........................ 26

--- Page 4 ---
Technical Reference MICROSAR VStdLib 
2015, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.9.0 
4 / 26 
Illustrations 
Figure 2-1 AUTOSAR 4.x Architecture Overview ................................ ......................... 6 
Figure 2-2 Interfaces to adjacent modules ................................ ................................ ... 7 
Figure 4-1 Include Structure ................................ ................................ ........................ 9 
 
 
Tables 
Table 1-1  Component history................................ ................................ ...................... 5 
Table 3-1  Service IDs ................................ ................................ ................................ . 8 
Table 3-2  Errors reported to DET ................................ ................................ ............... 8 
Table 4-1  Static files ................................ ................................ ................................ ... 9 
Table 4-2  Compiler Abstraction and Memory Mapping ................................ ............. 10 
Table 5-1  VStdLib_GetVersionInfo ................................ ................................ ........... 12 
Table 5-2  VStdLib_MemClr ................................ ................................ ...................... 13 
Table 5-3  VStdLib_MemClrMacro ................................ ................................ ............. 14 
Table 5-4  VStdLib_MemSet ................................ ................................ ...................... 15 
Table 5-5  VStdLib_MemSetMacro ................................ ................................ ............ 16 
Table 5-6  VStdLib_MemCpy ................................ ................................ ..................... 17 
Table 5-7  VStdLib_MemCpy16 ................................ ................................ ................. 18 
Table 5-8  VStdLib_MemCpy32 ................................ ................................ ................. 19 
Table 5-9  VStdLib_MemCpy_s ................................ ................................ ................. 20 
Table 5-10  VStdLib_MemCpyMacro ................................ ................................ ........... 21 
Table 5-11  VStdLib_MemCpyMacro_s ................................ ................................ ....... 22 
Table 5-12  Services used by VStdLib ................................ ................................ ......... 22 
Table 6-1  General configuration ................................ ................................ ............... 24 
Table 7-1  Abbreviations ................................ ................................ ............................ 25

--- Page 5 ---
Technical Reference MICROSAR VStdLib 
2015, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.9.0 
5 / 26 
1 Component History 
The component history gives an overview over the important milestones that are 
supported in the different versions of the component.  
Component Version New Features 
1.00 Creation of the component. 
2.00 Detach the component from core-based implementations, give optimized 
routines and support operations on large data (> 65535 bytes). 
Table 1-1  Component history

--- Page 6 ---
Technical Reference MICROSAR VStdLib 
2015, Vector Informatik GmbH Version: 1.00.00 
based on template version 5.9.0 
6 / 26 
2 Introduction 
This document describes the  functionality, API and configuration of the generic Vector 
Standard Library (VStdLib).  
 
Supported AUTOSAR Release*: 4.x 
Supported Configuration Variants: pre-compile 
Vendor ID: VSTDLIB_VENDOR_ID 30 decimal 
(= Vector-Informatik, 
according to HIS) 
Module ID: VSTDLIB_MODULE_ID 255 decimal 
(according to [1]) 
* For the precise AUTOSAR Release 4.x please see the release specific documentation. 
 
The VStdLib provide s a hardware independent implementation of memory manipulation  
services used by several MICROSAR BSW components. 
2.1 Architecture Overview 
The following figure shows where the VStdLib is located in the AUTOSAR architecture. 
 
Figure 2-1 AUTOSAR 4.x Architecture Overview

[… 20 further page(s) not extracted …]
