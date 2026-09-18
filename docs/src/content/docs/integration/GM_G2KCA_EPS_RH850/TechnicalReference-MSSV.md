---
title: "Top-Level Controller Project (G2KCA Electric Power Steering on RH850) — TechnicalReference MSSV"
description: "Converted Technical Reference (vendor) from TechnicalReference_MSSV.pdf (PDF, 623 KB)."
---

:::note
Converted from `GM_G2KCA_EPS_RH850/tools/SIP/Doc/TechnicalReferences/TechnicalReference_MSSV.pdf` (Technical Reference (vendor); original PDF, about 623 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_G2KCA_EPS_RH850](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR Safe Silence Verifier 
Technical Reference 
 
 
Version 1.4 
 
 
 
 
 
 
 
 
 
 
 
Authors Markus Groß, Patrick Markl 
Status Released

--- Page 2 ---
Technical Reference MICROSAR Safe Silence Verifier 
2014, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
2 / 22 
Document Information 
History 
Author Date Version Remarks 
Markus Groß 2012-07-24 1.0 Initial version 
Patrick Markl 2012-08-22 1.1 Changes after review 
Markus Groß 2012-11-15 1.2 Add information about third party libraries 
Markus Groß 2013-01-15 1.3 Update to reflect changes 
Patrick Markl 2014-03-03 1.4 Added restrictions chapter 
Reference Documents 
No. Source Title Version 
[1]  ISO ISO/IEC 9899:1990, Programming languages -C Second 
edition

--- Page 3 ---
Technical Reference MICROSAR Safe Silence Verifier 
2014, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
3 / 22 
Contents 
1 Introduction................................ ................................ ................................ ................... 6 
1.1 Intended audience ................................ ................................ ............................. 6 
2 Functional Description ................................ ................................ ................................ . 7 
2.1 Required Environment ................................ ................................ ....................... 7 
2.2 Restrictions ................................ ................................ ................................ ........ 7 
2.3 Command Line Parameters ................................ ................................ ............... 7 
2.3.1 Option -h, --help ................................ ................................ ................. 8 
2.3.2 Option --version ................................ ................................ ................. 8 
2.3.3 Option -v, --verbose ................................ ................................ ............ 8 
2.3.4 Option --crcCheck ................................ ................................ .............. 8 
2.3.5 Option --openReport ................................ ................................ .......... 8 
2.3.6 Option --stats ................................ ................................ ................ 8 
2.3.7 Option -l, --logFile ................................ ................................ .............. 8 
2.3.8 Option -r, --reportFile ................................ ................................ .......... 9 
2.3.9 Option -p, --pluginDir ................................ ................................ .......... 9 
2.3.10 Option -D, --define ................................ ................................ ............. 9 
2.3.11 Option –i, --inputDir ................................ ................................ ............ 9 
2.3.12 Command Line Usage ................................ ................................ ....... 9 
2.3.12.1 Option Only Parameters ................................ .................. 9 
2.3.12.2 Parameters Requiring A Value ................................ ....... 10 
2.3.12.3 Examples ................................ ................................ ....... 10 
3 Analysis Report ................................ ................................ ................................ .......... 11 
3.1.1 Structure ................................ ................................ .......................... 11 
3.1.1.1 Header ................................ ................................ ........... 11 
3.1.1.2 Information about Environment ................................ ...... 11 
3.1.1.3 Detailed Log Output ................................ ....................... 11 
3.2 Error Messages ................................ ................................ ...............................  12 
3.3 Steps if the Analysis Fails ................................ ................................ ................ 13 
4 Integration ................................ ................................ ................................ ................... 14 
4.1 Deliverables ................................ ................................ ................................ ..... 14 
4.2 GENy ................................ ................................ ................................ ............... 14 
4.3 DaVinci Configurator Pro 5................................ ................................ ............... 16 
5 Third Party Libraries ................................ ................................ ................................ ... 18 
5.1 Boost ................................ ................................ ................................ ............... 18 
5.2 ChaiScript 

--- Page 4 ---
Technical Reference MICROSAR Safe Silence Verifier 
2014, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
4 / 22 
5.3 LLVM/Clang ................................ ................................ ................................ ..... 19 
5.4 OpenBSD regex ................................ ................................ ...............................  20 
6 Contact ................................ ................................ ................................ ........................ 22

--- Page 5 ---
Technical Reference MICROSAR Safe Silence Verifier 
2014, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
5 / 22 
Tables 
Table 2-1  Command Line Parameters ................................ ................................ ........ 8 
Table 3-1  Message classes and their value ................................ ..............................  13 
Table 4-1  Locations of Deliverables in an SIP ................................ .......................... 14

--- Page 6 ---
Technical Reference MICROSAR Safe Silence Verifier 
2014, Vector Informatik GmbH Version: 1.4 
based on template version 4.11.3 
6 / 22 
1 Introduction 
MICROSAR Safe Silence Verifier (MSS V) is a command line tool delivered as part of 
Silent BSW packages. MSSV checks based on rules the consistency of generated 
configuration files of the BSW modules.  The result is written to a HTML report.  The report 
is part of the proof that the BSW modules fulfill the Freedom from Interference criteria. 
  
 
Reference 
For all required steps to be performed as part of the Silent BSW integration see the 
project specific Safety Manual. 
  
1.1 Intended audience 
This document is relevant for developers who integrate Silent BSW into their ECU.

[… 16 further page(s) not extracted …]
