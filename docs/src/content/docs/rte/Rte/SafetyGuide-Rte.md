---
title: "Runtime Environment — SafetyGuide Rte"
description: "Converted Safety Manual / Safety Case from SafetyGuide_Rte.pdf (PDF, 785 KB)."
---

:::note
Converted from `Rte/doc/SafetyGuide_Rte.pdf` (Safety Manual / Safety Case; original PDF, about 785 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Rte](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR RTE 
Safety Guide 
 
  
Version 4.8.0 
 
 
 
 
 
 
 
 
 
 
 
Authors Sascha Sommer, Bernd Sigle 
Status Released

--- Page 2 ---
Safety Guide MICROSAR RTE 
2015, Vector Informatik GmbH Version: 4.8 
based on template version 4.8.0 
2 / 76 
Document Information 
History 
Author Date Version Remarks 
4.1.0 2013-04-15 Sascha 
Sommer 
Initial Creation for RTE 4.1 (AUTOSAR 4) 
4.2.0 2013-10-29 Sascha 
Sommer 
Bernd Sigle 
Updated for RTE 4.2 
Explained MICROSAR OS interrupt locking 
APIs. 
Corrected review findings especially the 
used abbreviations. 
4.3.0 2014-02-05 Sascha 
Sommer 
Updated for RTE 4.3 
Clarified Assumptions about VFB Trace 
Hooks 
Described Inter-ECU sender/receiver from 
the ASIL partition 
Support for mapped client/server calls 
between partitions 
Multicore Support 
SuspendAllInterrupts is no longer used 
4.4.0 2014-06-11 Sascha 
Sommer 
Updated for RTE 4.4 
4.5.0 2014-10-15 Bernd Sigle Updated for RTE 4.5 
Rte_DRead added  
4.6.0 2014-12-10 Sascha 
Sommer 
Updated for RTE 4.6 
4.7.0 2015-03-18 Sascha 
Sommer 
Updated for RTE 4.7 
4.8.0 2015-07-15 Sascha 
Sommer 
Updated for RTE 4.8 
Described APIs/scheduling of ASIL BSW 
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_SWS_RTE.pdf  
3.2.0 
[2]  AUTOSAR AUTOSAR_SWS_OS.pdf  
5.0.0 
[3]  AUTOSAR AUTOSAR_SWS_StandardTypes.pdf  
1.3.0 
[4]  AUTOSAR AUTOSAR_SWS_PlatformTypes.pdf  
2.5.0 
[5]  AUTOSAR AUTOSAR_SWS_CompilerAbstraction.pdf  
3.2.0

--- Page 3 ---
Safety Guide MICROSAR RTE 
2015, Vector Informatik GmbH Version: 4.8 
based on template version 4.8.0 
3 / 76 
[6]  AUTOSAR AUTOSAR_SWS_MemoryMapping.pdf  
 
[7]  Vector Technical Reference MICROSAR RTE 4.8.0 
[8]  ISO ISO/DIS 26262 2009 
 
Scope of the Document  
This document describes the use of the MICROSAR RTE with regards to functional safety. 
All general aspects of the MICROSAR RTE  are described in a separate document [7], 
which is also part of the delivery. 
 
 
 
 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
Safety Guide MICROSAR RTE 
2015, Vector Informatik GmbH Version: 4.8 
based on template version 4.8.0 
4 / 76 
Contents 
1 Purpose................................ ................................ ................................ ........................... 8 
2 Assumptions on the scope of the MICROSAR RTE ................................ ..................... 9 
2.1 MICROSAR RTE overview ................................ ................................ .............. 9 
2.2 Standards and Legal requirements ................................ ................................  10 
2.3 Functions of the MICROSAR RTE ................................ ................................ . 10 
2.4 Operating conditions ................................ ................................ ..................... 15 
2.5 Assumptions ................................ ................................ ................................ . 16 
3 Assumptions on the safety goals of the MICROSAR RTE ................................ ......... 20 
4 Safety concept of the MICROSAR RTE ................................ ................................ ....... 21 
4.1 Functional concept ................................ ................................ ........................ 21 
4.2 Safe state and degradation concept ................................ ..............................  22 
4.3 Fault tolerance and diagnostics concept................................ ........................ 22 
5 Integration of the MICROSAR RTE in a new particular context ................................  23 
5.1 Assumptions ................................ ................................ ................................ . 23 
5.2 RTE Configuration ................................ ................................ ......................... 27 
5.3 RTE Generation ................................ ................................ ............................ 30 
6 Qualification of generated RTE Code ................................ ................................ ......... 31 
6.1 Introduction ................................ ................................ ................................ ... 31 
6.2 Compiler and Memory Abstraction ................................ ................................ . 32 
6.3 DataTypes ................................ ................................ ................................ ..... 33 
6.3.1 Imported Types ................................ ................................ ............................. 33 
6.3.2 Application Types Generated by the RTE ................................ ...................... 34 
6.3.3 Handling of Array and String Data Types ................................ ....................... 34 
6.3.4 Datatype specific handling of Interrupt Locks and Spinlocks ......................... 34 
6.4 SWC Implementation ................................ ................................ .................... 37 
6.5 BSW Implementation ................................ ................................ ..................... 39 
6.6 SWC specific RTE APIs................................ ................................ ................. 40 
6.6.1 Rte_Write ................................ ................................ ................................ ...... 40 
6.6.1.1 Configuration Variant Intra-ECU Without IsUpdated ................................ ...... 40 
6.6.1.2 Generated Code Intra-ECU Without IsUpdated ................................ ............. 40 
6.6.1.3 Configuration Variant Intra-ECU With IsUpdated ................................ ........... 42 
6.6.1.4 Generated Code Intra-ECU With IsUpdated ................................ .................. 43 
6.6.1.5 Configuration Variant Inter-ECU ................................ ................................ .... 45 
6.6.1.6 Generated Code Inter-ECU ................................ ................................ ........... 45

--- Page 5 ---
Safety Guide MICROSAR RTE 
2015, Vector Informatik GmbH Version: 4.8 
based on template version 4.8.0 
5 / 76 
6.6.2 Rte_Read ................................ ................................ ................................ ...... 47 
6.6.2.1 Configuration Variant Without IsUpdated ................................ ....................... 47 
6.6.2.2 Generated Code Without IsUpdated ................................ ..............................  48 
6.6.2.3 Configuration Variant With IsUpdated ................................ ............................ 50 
6.6.2.4 Generated Code With IsUpdated................................ ................................ ... 50 
6.6.3 Rte_IsUpdated ................................ ................................ ..............................  53 
6.6.3.1 Configuration Variant ................................ ................................ ..................... 53 
6.6.3.2 Generated Code ................................ ................................ ............................ 53 
6.6.4 Rte_IrvWrite ................................ ................................ ................................ .. 55 
6.6.4.1 Configuration Variant ................................ ................................ ..................... 55 
6.6.4.2 Generated Code ................................ ................................ ............................ 55 
6.6.5 Rte_IrvRead ................................ ................................ ................................ .. 57 
6.6.5.1 Configuration Variant ................................ ................................ ..................... 57 
6.6.5.2 Generated Code ................................ ................................ ............................ 57 
6.6.6 Rte_Pim ................................ ................................ ................................ ........ 59 
6.6.6.1 Configuration Variant ................................ ................................ ..................... 59 
6.6.6.2 Generated Code ................................ ................................ ............................ 59 
6.6.7 Rte_CData ................................ ................................ ................................ .... 60 
6.6.7.1 Configuration Variant ................................ ................................ ..................... 60 
6.6.7.2 Generated Code ................................ ................................ ............................ 60 
6.6.8 Rte_Prm ................................ ................................ ................................ ........ 61 
6.6.8.1 Configuration Variant ...................

[… 70 further page(s) not extracted …]
