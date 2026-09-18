---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference Asr MemoryMapping"
description: "Converted Technical Reference (vendor) from TechnicalReference_Asr_MemoryMapping.pdf (PDF, 476 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_Asr_MemoryMapping.pdf` (Technical Reference (vendor); original PDF, about 476 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR Memory Mapping 
Technical Reference 
 
 
Version 1.0.1 
 
 
 
 
 
 
 
 
 
 
 
Authors Eugen Stripling 
Status Released

--- Page 2 ---
Technical Reference MICROSAR Memory Mapping 
2013, Vector Informatik GmbH Version: 1.0.1 
based on template version 5.6.0 
2 / 19 
Document Information 
History 
Author Date Version Remarks 
Eugen Stripling 2013-04-12 1.00.00 Creation - ESCAN00064655 
Eugen Stripling 2013-05-29 1.00.01 Some typos corrected 
    
Reference Documents 
No. Source Title Version 
[1]  AUTOSAR AUTOSAR_SWS_MemoryMapping.pdf 1.4.0 
[2]  AUTOSAR AUTOSAR_SWS_CompilerAbstraction.pdf 3.2.0 
 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference MICROSAR Memory Mapping 
2013, Vector Informatik GmbH Version: 1.0.1 
based on template version 5.6.0 
3 / 19 
Contents 
1 Introduction................................ ................................ ................................ ................... 5 
2 Functional Description ................................ ................................ ................................ . 6 
2.1 Memory section keywords ................................ ................................ .................. 6 
2.1.1 Declaration of code and data segments in AUTOSAR ........................ 7 
2.1.2 Mapping of code and data segments to a dedicated memory area ..... 7 
2.1.3 Example: Mapping of data to a post-build memory section................. 8 
3 Appendix ................................ ................................ ................................ ..................... 12 
3.1 Sub-keywords used in the memory section and compiler specific keywords .... 12 
3.2 Memory section keywords ................................ ................................ ................ 12 
3.2.1 Memory section keywords for code ................................ .................. 13 
3.2.2 Memory section keywords for constants ................................ ........... 13 
3.2.3 Memory section keywords for variables................................ ............ 14 
3.3 Compiler specific keywords ................................ ................................ .............. 16 
4 Glossary and Abbreviations ................................ ................................ ...................... 18 
4.1 Glossary ................................ ................................ ................................ .......... 18 
4.2 Abbreviations ................................ ................................ ................................ ... 18 
5 Contact ................................ ................................ ................................ ........................ 19

--- Page 4 ---
Technical Reference MICROSAR Memory Mapping 
2013, Vector Informatik GmbH Version: 1.0.1 
based on template version 5.6.0 
4 / 19 
Illustrations 
Figure 2-1  Files MemMap.h and Compiler_Cfg.h ................................ ........................ 6 
 
Tables 
Table 3-1  Explanation of sub-keywords used in the memory section and compiler 
specific keywords ................................ ................................ ..................... 12 
Table 3-2  Memory sections for code ................................ ................................ ......... 13 
Table 3-3  Memory sections for constants ................................ ................................ . 13 
Table 3-4  Change of memory section keywords for constants in ASR 4.0.3 ............. 14 
Table 3-5  Memory sections for variables ................................ ................................ .. 15 
Table 3-6 Change of memory section keywords for variables in ASR 4.0.3 .............. 16 
Table 3-7  Compiler specific keywords and the related memory sections they used 
for ................................ ................................ ................................ ............. 17 
Table 4-1  Glossary ................................ ................................ ................................ ... 18 
Table 4-2  Abbreviations ................................ ................................ ............................ 18

--- Page 5 ---
Technical Reference MICROSAR Memory Mapping 
2013, Vector Informatik GmbH Version: 1.0.1 
based on template version 5.6.0 
5 / 19 
1 Introduction 
This document gives an overview about the functionality of memory mapping as specified 
by AUTOSAR according to the Vector specific implementation (MICROSAR).

--- Page 6 ---
Technical Reference MICROSAR Memory Mapping 
2013, Vector Informatik GmbH Version: 1.0.1 
based on template version 5.6.0 
6 / 19 
2 Functional Description 
In the following chapters the following two expressions are used: 
 memory section keyword 
and  
 memory area. 
A memory section keyword  describes a memory section according to AUTOSAR 
symbolically. All available corresponding keywords are described in chapter 3.2. By 
memory area a memory section in hardware at all is meant. 
By using of expression build-toolchain the functionality covered by a comp iler, linker and  
locator is meant. 
2.1 Memory section keywords 
The keywords of memory section s of all BSW -modules are collected and located in file 
MemMap.h. 
The file Compiler_Cfg.h contains additional compiler specific keywords. These 
keywords are used to describe t he memory location of variables, constants and pointers.  
In case of pointer s additional keywords are defined to describe  the memory location the 
pointer points to. 
Both files are provided as templates and are named _MemMap.h and _Compiler_Cfg.h 
initially. Before using both files have to be renamed to MemMap.h and Compiler_Cfg.h 
respectively. 
 
Figure 2-1  Files MemMap.h and Compiler_Cfg.h 
 
Each BSW-module has its own set of compiler specific and memory section keywords with 
the pre-fix <MSN>. By default all the memory section  keywords are mapped to the same 
default memory section keyword defined in MemMap.h. If required the default mapping can 
be modified by the BSW integrator.  Detailed information concerning the provided memory 
class Feature
MemMap.h Compiler_Cfg.h
contains #pragma 
commands for memory 
allocation
contains compiler 
specific keywords for 
description of location 
of variables, costants 
and pointers

[… 13 further page(s) not extracted …]
