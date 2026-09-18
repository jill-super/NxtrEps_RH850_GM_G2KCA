---
title: "DaVinci Configuration Support — TechnicalReference DataTypes AR4"
description: "Converted Technical Reference (vendor) from TechnicalReference_DataTypes_AR4.pdf (PDF, 3863 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Docs/TechnicalReference_DataTypes_AR4.pdf` (Technical Reference (vendor); original PDF, about 3863 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Technical Reference Autosar 4.0 - DataTypes 
2014, Vector Informatik GmbH Version: 1.1 
based on template version 5.1.0 
1 / 80 
 
 
 
 
 
 
 
 
 
 
 
Autosar 4.0 - DataTypes 
Technical Reference 
 
 
Version 1.1 
 
 
 
 
 
 
 
 
 
 
Authors Thomas Bruni 
Status Released

--- Page 2 ---
Technical Reference Autosar 4.0 - DataTypes 
2014, Vector Informatik GmbH Version: 1.1 
based on template version 5.1.0 
2 / 80 
Document Information 
History 
Author Date Version Remarks 
Thomas Bruni 11.11.2013 0.1 Document creation 
Thomas Bruni 14.01.2014 0.2 Changes: 
3.4 Platform types 
 
Thomas Bruni 27.01.2014 0.3 Corrections in 3.4 Platform 
types 
Thomas Bruni 29.01.2014 0.4 Creation of 2  new chapter s: 
3.4 Data type mapping 
5.4 Data type mapping 
assistant 
5.5 Type emitter 
Thomas Bruni 21.02.2014 1.0 Release version 
Thomas Bruni 14.03.2014 1.1 Changes for Mode 
Declaration Group mapping : 
chapters 3.4 and 4.4. 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_TPS_SoftwareComponentTemplate 4.2.0 
[2]  AUTOSAR AUTOSAR_SWS_PlatformTypes 2.5.0

--- Page 3 ---
Technical Reference Autosar 4.0 - DataTypes 
2014, Vector Informatik GmbH Version: 1.1 
based on template version 5.1.0 
3 / 80 
Contents 
1 Introduction ................................ ................................ ................................ .................... 6 
2 Data Types and Data Prototypes ................................ ................................ ................... 7 
3 Design of data prototypes in DaVinci tool chain ................................ .......................... 8 
3.1 Data prototypes ................................ ................................ ................................ ........ 8 
3.2 Application data types ................................ ................................ ............................ 10 
3.3 Implementation data types ................................ ................................ ..................... 11 
3.4 Data type mapping ................................ ................................ ................................ . 14 
3.5 Platform types ................................ ................................ ................................ ........ 15 
3.5.1 Definitions ................................ ................................ ................................ ..... 15 
3.5.1.1 Autosar Standard Types ................................ ................................ ......... 15 
3.5.1.2 Platform Types ................................ ................................ ....................... 15 
3.5.1.3 Valid C expression ................................ ................................ .................. 15 
3.5.2 Practice ................................ ................................ ................................ ......... 16 
3.5.2.1 Abstraction of SW from platform ................................ ............................. 16 
3.5.2.2 Dependency between SW and platform ................................ ................. 17 
3.5.2.3 Platform types and Vector DaVinci Tool suite ................................ .......... 18 
3.6 Generation ................................ ................................ ................................ ............. 22 
4 Design examples ................................ ................................ ................................ .......... 23 
4.1 Primitive data element ................................ ................................ ............................ 23 
4.2 Complex data element ................................ ................................ ........................... 36 
4.3 Enumeration ................................ ................................ ................................ ........... 48 
4.3.1 Application level ................................ ................................ ............................ 48 
4.3.2 Implementation level ................................ ................................ ..................... 52 
4.4 Mode declaration ................................ ................................ ................................ .... 55 
4.4.1 Mode declaration group in DaVinci Developer ................................ ............... 55 
4.4.2 Mode service port in BswM configuration ................................ ...................... 59 
4.4.3 Mode request port and mapping ................................ ................................ .... 62 
4.5 Implementation data type examples ................................ ................................ ....... 66 
4.5.1 Type reference ................................ ................................ ..............................  66 
4.5.2 Value ................................ ................................ ................................ ............. 67 
5 Additional information ................................ ................................ ................................ . 69 
5.1 Compatibility and conversion ................................ ................................ .............

--- Page 4 ---
Technical Reference Autosar 4.0 - DataTypes 
2014, Vector Informatik GmbH Version: 1.1 
based on template version 5.1.0 
4 / 80 
5.5 Type emitter ................................ ................................ ................................ ........... 78 
6 Glossary and Abbreviations ................................ ................................ ........................ 79 
6.1 Glossary ................................ ................................ ................................ ................. 79 
6.2 Abbreviations ................................ ................................ ................................ ......... 79 
7 Contact................................ ................................ ................................ .......................... 80 
 
Illustrations 
Figure 3-1 S/R port interface element ................................ ................................ .......... 9 
Figure 3-2 S/R port interface element init value ................................ ........................... 9 
Figure 3-3 DaVinci Developer – workspace library ................................ ..................... 10 
Figure 3-4 Application data type categories ................................ ...............................  10 
Figure 3-5 Application data type Value property dialog ................................ .............. 11 
Figure 3-6 Implementation data type categories ................................ ........................ 12 
Figure 3-7 Implementation data type Value property dialog ................................ ....... 13 
Figure 3-8 2 ways of modelling platform independent implementation data types ...... 17 
Figure 3-9 Modelling a platform specific implementation data type ............................ 18 
Figure 3-10 Platform Types in DaVinci Developer ................................ ........................ 19 
Figure 3-11 Implementation data type referencing a platform type ...............................  19 
Figure 3-12 Native declaration: Autosar Standard Type ................................ ............... 20 
Figure 3-13 Native declaration: valid C expression ................................ ...................... 21 
Figure 4-1 New Value application data type ................................ ...............................  24 
Figure 4-2 My_TemperatureType ................................ ................................ ............... 25 
Figure 4-3 My_TemperatureType_CompuMethod ................................ ...................... 25 
Figure 4-4 Celsius unit ................................ ................................ ...............................  26 
Figure 4-5 Physical to Internal linear scale ................................ ................................  26 
Figure 4-6 Physical constraint ................................ ................................ .................... 27 
Figure 4-7 Type mapping set creation ................................ ................................ ........ 28 
Figure 4-8 Type mapping set naming ................................ ................................ ......... 28 
Figure 4-9 Add a data type mapping to a type mapping set ................................ ....... 29 
Figure 4-10 My_TemperatureInterface ................................ ................................ ......... 30 
Figure 4-11 My_TemperatureElement ................................ ................................ .......... 30 
Figure 4-12 SWC_Sender modeling ................................ ................................ ............ 31 
Figure 4-13 SWC_Receiver modeling ................................ ................................ .......... 32 
Figure 4-14 Connection of My_TemperatureInterface ports ................................ ......... 33 
Figure 4-15 Missing data type mapping error message ................................ 

[… 74 further page(s) not extracted …]
