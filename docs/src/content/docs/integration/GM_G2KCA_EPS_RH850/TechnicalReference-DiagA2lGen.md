---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference DiagA2lGen"
description: "Converted Technical Reference (vendor) from TechnicalReference_DiagA2lGen.pdf (PDF, 197 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_DiagA2lGen.pdf` (Technical Reference (vendor); original PDF, about 197 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR Diag A2l Gen 
Technical Reference 
 
A2l fragment file generator for DEM, DCM and FIM 
Version 1.01.01 
 
 
 
 
 
 
 
 
 
 
 
Authors Alexander Ditte 
Status Released

--- Page 2 ---
Technical Reference MICROSAR Diag A2l Gen 
2013, Vector Informatik GmbH Version: 1.01.01 
based on template version 4.8.3 
2 / 9 
Document Information 
History 
Author Date Version Remarks 
Alexander Ditte 2012-04-13 01.00.00 initial version 
Alexander Ditte 2013-06-12 01.01.00 added support for AR4 DCM 
Alexander Ditte 2013-09-25 01.01.01 update of chapter 3.1 
Reference Documents 
No. Source Title Version 
- - - - 
Scope of the Document  
This technical reference describes the specific use of the  diagnostic A2l frag ment file 
generator for the DEM, DCM and FIM modules. 
 
 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR Diag A2l Gen 
2013, Vector Informatik GmbH Version: 1.01.01 
based on template version 4.8.3 
3 / 9 
Contents 
1 Component History ................................ ................................ ................................ ........ 5 
2 Introduction ................................ ................................ ................................ .................... 6 
3 Functional Description ................................ ................................ ................................ .. 7 
3.1 Features ................................ ................................ ................................ .......... 7 
4 Glossary and Abbreviations ................................ ................................ .......................... 8 
4.1 Glossary ................................ ................................ ................................ .......... 8 
4.2 Abbreviations ................................ ................................ ................................ .. 8 
5 Contact ................................ ................................ ................................ ............................ 9

--- Page 4 ---
Technical Reference MICROSAR Diag A2l Gen 
2013, Vector Informatik GmbH Version: 1.01.01 
based on template version 4.8.3 
4 / 9 
Tables 
Table 1-1  Component history................................ ................................ ...................... 5 
Table 3-1 Command line arguments ................................ ................................ ........... 7 
Table 4-1  Glossary ................................ ................................ ................................ ..... 8 
Table 4-2  Abbreviations ................................ ................................ ..............................  8

--- Page 5 ---
Technical Reference MICROSAR Diag A2l Gen 
2013, Vector Informatik GmbH Version: 1.01.01 
based on template version 4.8.3 
5 / 9 
1 Component History 
The component history gives an overview over the important milestones that are 
supported in the different versions of the component.  
Component Version New Features 
01.00.00 > Initial version  
01.01.00 > Added support for selective generation of measurement or calibration 
fragment content only 
01.02.00 > Added support for AUTOSAR 4 DCM 
> Type definition template is generated in an own file 
Table 1-1  Component history

--- Page 6 ---
Technical Reference MICROSAR Diag A2l Gen 
2013, Vector Informatik GmbH Version: 1.01.01 
based on template version 4.8.3 
6 / 9 
2 Introduction 
This document describes the functionality, API and configuration of the diagnostic A2l 
fragment generator module. 
This generator shall support the customer to calibrate pre -defined symbols of the following 
modules: 
 
Specification 
 
 
 
Component 
MICROSAR 3 
MICROSAR 4 
DEM   
DCM   
FIM   
Table 2-1  Supported components and specifications

[… 3 further page(s) not extracted …]
