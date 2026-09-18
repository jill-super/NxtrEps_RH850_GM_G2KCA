---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference ComStackLib"
description: "Converted Technical Reference (vendor) from TechnicalReference_ComStackLib.pdf (PDF, 791 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_ComStackLib.pdf` (Technical Reference (vendor); original PDF, about 791 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR ComStackLib 
Technical Reference 
 
ComStackLib based BSW generators 
Version 2.00.01 
 
 
 
 
 
 
 
 
 
 
 
Authors Gunnar Meiss 
Status Released

--- Page 2 ---
Technical Reference MICROSAR ComStackLib  
2014, Vector Informatik GmbH Version: 2.00.01 
based on template version 5.5.0 
2 / 37 
Document Information 
History 
Author Date Version Remarks 
Gunnar Meiss 2013-03-25 1.00.00 initial version 
Gunnar Meiss 2013-08-23 1.01.00 ESCAN00068919 Remove 
<MSN>UseSignedDataTypesInIndexArrays 
ESCAN00070017 Remove <MSN>_Resource.xml 
Gunnar Meiss 2014-10-06 2.00.00 ESCAN00078776 AR4-698: Post-Build Selectable 
(Identity Manager) 
Gunnar Meiss 2014-12-19 2.00.01 ESCAN00080380 Minor typing and grammar corrections 
Reference Documents 
No. Source Title Version 
[1]  Vector Compliance Documentation MISRA-C:2004 / MICROSAR 2.2.0 
Scope of the Document 
This technical reference describes the general use of the ComStackLib based BSW 
generators. 
 
 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR ComStackLib  
2014, Vector Informatik GmbH Version: 2.00.01 
based on template version 5.5.0 
3 / 37 
Contents 
1 Component History ................................ ................................ ................................ ...... 5 
2 Introduction................................ ................................ ................................ ................... 6 
2.1 Architecture Overview ................................ ................................ ........................ 7 
3 Functional Description ................................ ................................ ................................ . 8 
3.1 CONFIG-CLASS of Data ................................ ................................ .................... 9 
3.2 CONFIG-CLASS PRE-COMPILE Optimizations ................................ ................ 9 
3.2.1 Optimize Const Data to Defines ................................ ......................... 9 
3.2.2 Optimize Data Types ................................ ................................ ........ 10 
3.2.3 Optimize Bool Data in Structs ................................ .......................... 11 
3.2.4 Data Deduplication and Reduction ................................ ................... 12 
3.2.4.1 Equal Data ................................ ................................ ..... 13 
3.2.4.2 Unary and Binary Operations ................................ ......... 14 
3.2.5 Data Streaming ................................ ................................ ................ 15 
3.3 CONFIG-CLASS Independent Optimizations ................................ ................... 16 
3.3.1 Sort Struct Elements ................................ ................................ ........ 16 
3.4 SELECTABLE Optimizations ................................ ................................ ............ 17 
3.4.1 Merge of VAR and CONST Based Data ................................ ........... 17 
4 Integration ................................ ................................ ................................ ................... 18 
4.1 Dynamic Files ................................ ................................ ................................ .. 18 
4.2 IMPLEMENTATION-CONFIG-VARIANT dependent Data ................................  20 
4.3 Optimization Levels ................................ ................................ .......................... 21 
4.4 MISRA, PRQA and Compiler Warnings ................................ ............................ 23 
4.4.1 General ................................ ................................ ............................ 23 
4.4.2 Bitfields ................................ ................................ ............................ 28 
4.4.3 <MSN>_Has Macros in the SELECTABLE Use Case ...................... 29 
5 Configuration ................................ ................................ ................................ .............. 30 
5.1 Configuration Variants ................................ ................................ ...................... 30 
5.2 Configuration with a GCE ................................ ................................ ................. 30 
6 Glossary and Abbreviations ................................ ................................ ...................... 36 
6.1 Glossary ................................ ................................ ................................ .......... 36 
6.2 Abbreviations ................................ ................................ ................................ ... 36 
7 Contact ................................ ................................ ................................ ........................ 37

--- Page 4 ---
Technical Reference MICROSAR ComStackLib  
2014, Vector Informatik GmbH Version: 2.00.01 
based on template version 5.5.0 
4 / 37 
Illustrations 
Figure 2-1 Embedded Code Aspects ................................ ................................ ........... 6 
Figure 2-2 AUTOSAR 4.x Architecture Overview ................................ ......................... 7 
Figure 3-1 Resources in compiler optimization variants ................................ ............... 8 
Figure 3-2 Using defines for CONST data ................................ ................................ .... 9 
Figure 3-3 Data type minimization ................................ ................................ ............. 10 
Figure 3-4 Boolean struct data variants ................................ ................................ ..... 11 
Figure 3-5 Boolean struct data versus Bitmasking ................................ ..................... 12 
Figure 3-6 Data deduplication without operations ................................ ...................... 13 
Figure 3-7 Data deduplication with operations ................................ ........................... 14 
Figure 3-8 Data Streaming ................................ ................................ ......................... 15 
Figure 3-9 Sorting struct elements ................................ ................................ ............. 16 
Figure 4-1 Resources in optimization variants ................................ ........................... 21 
 
Tables 
Table 1-1  Component history................................ ................................ ...................... 5 
Table 4-1  Generated files ................................ ................................ ......................... 19 
Table 4-2  IMPLEMENTATION-CONFIG-VARIATIONS ................................ ............. 20 
Table 4-3  Optimization Levels ................................ ................................ .................. 21 
Table 4-4  Optimization Decision Table ................................ ................................ ...... 22 
Table 4-5  MD_CSL_3199 ................................ ................................ ......................... 23 
Table 4-6  MD_CSL_750_759 ................................ ................................ ................... 24 
Table 4-7  MD_CSL_0779 ................................ ................................ ......................... 25 
Table 4-8  MD_CSL_2018 ................................ ................................ ......................... 26 
Table 4-9  MD_CSL_3355_3356 ................................ ................................ ............... 26 
Table 4-10  MD_CSL_3453 ................................ ................................ ......................... 27 
Table 4-11  /MICROSAR/EcuC/EcucGeneral/BitFieldDataType ................................ .. 28 
Table 5-1  Container ................................ ................................ ................................ .. 30 
Table 5-2  Attributes of ComStackLib based BSW generators ................................ ... 35 
Table 6-1  Glossary ................................ ................................ ................................ ... 36 
Table 6-2  Abbreviations ................................ ................................ ............................ 36

--- Page 5 ---
Technical Reference MICROSAR ComStackLib  
2014, Vector Informatik GmbH Version: 2.00.01 
based on template version 5.5.0 
5 / 37 
1 Component History 
The component history gives an overview over the important milestones that are 
supported in the different versions of the component.  
Component Version New Features 
1.00.00 Support of embedded data generation in the 
IMPLEMENTATION-CONFIG-VARIANT VARIANT-PRE-COMPILE 
2.00.00 Support of the 
IMPLEMENTATION-CONFIG-VARIANT VARIANT-POST-BUILD-
LOADABLE 
3.00.00 Revision o

[… 31 further page(s) not extracted …]
