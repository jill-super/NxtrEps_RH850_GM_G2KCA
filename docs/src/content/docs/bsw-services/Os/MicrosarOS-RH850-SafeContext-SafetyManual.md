---
title: "Operating System — MicrosarOS RH850 SafeContext SafetyManual"
description: "Converted Safety Manual / Safety Case from MicrosarOS_RH850_SafeContext_SafetyManual.pdf (PDF, 951 KB)."
---

:::note
Converted from `Os/doc/MicrosarOS_RH850_SafeContext_SafetyManual.pdf` (Safety Manual / Safety Case; original PDF, about 951 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Os](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              1 / 80 
 
 
 
 
 
 
 
 
 
 
 
MICROSAR OS SafeContext 
Safety Manual 
 
RH850 with Green Hills Compiler 
 
 
 
 
 
 
 
 
 
 
 
Authors Senol Cendere, Yohan Humbert 
Version 1.05 
Status Released 
Document ID OS03.00124.10

--- Page 2 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              2 / 80 
Document Information 
History 
Author Date Version Remarks 
Senol Cendere  2014-02-17 1.00 Creation for RH850 
Senol Cendere 2014-02-26 1.01 Updated the Requirement IDs 
Senol Cendere 2014-05-09 1.02 Adaption for RH850 P1M 
Senol Cendere 2014-08-18 1.03 Reworked after Safety Manual Review 
Senol Cendere 2014-09-22 1.04 Added reference for Renesas Electronics RH850/P1M  
Safety Application Note 
Removed CPU derivative specification  
Removed compiler options (both are specified in safety 
case) 
Yohan Humbert 2014-12-03 1.05 Added level support 
[END OF HIST ORY]

--- Page 3 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              3 / 80

--- Page 4 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              4 / 80 
Reference Documents 
No. Source Title Version 
[1]   AUTOSAR Operating System Specification1 3.x - 
4.x 
[2]   OSEK/VDX Operating System Specification2 2.2.3 
[3]  Vector Informatik GmbH User manual of Vector MICROSAR OS 
TechnicalReference_Microsar_Os.pdf 
6.03 
[4]  Vector Informatik GmbH User manual of Vector MICROSAR OS RH850,  
hardware specific part 
TechnicalReference_MICROSAROS_RH850_S
afeContext.pdf 
1.04 
[5]   International Organization for Standardization, 
Draft International Standard ISO/DIS 26262 
Road Vehicles - Functional Safety (all parts), 
2009 
 
[6]  Renesas Electronics V850E3v5 Architecture Specifications (4th edition) 
[7]  Renesas Electronics  
 
RH850 G3M User’s Manual: Software 
r01us0042ej0020_rh850g3m.pdf 
Rev. 0.10 
Oct. 2012 
[8]  Renesas Electronics RH850/P1x Group User’s Manual: Hardware 
r01uh0436ej0041_rh850p1x.pdf 
Rev. 0.60 
Jul. 2014 
[9]  Green Hills Software MULTI: Building Applications for Embedded 
V850 and RH850 build_v800.pdf 
PubID: 
build_v800-
472243 
Date: 
September 12, 
2012 
[10]  Vector Informatik GmbH Vector MICROSAR OS SafeContext Concept 1.03 
[11]  Renesas Electronics RH850/P1M Safety Application Note Rev.0.20 
September 1, 
2014 
                                            
1 This document is available in PDF-format on the Internet at the Autosar homepage: http://www.Autosar.org 
2 This document is available in PDF-format on the Internet at the OSEK/VDX homepage: http://www.osek-vdx.org

--- Page 5 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              5 / 80 
Contents 
1 Purpose ................................ ................................ ................................ ......................... 9 
1.1 Safety Element out of Context (SEooC) ................................ ............................. 9 
1.2 Standards and Legal requirements ................................ ................................ .... 9 
2 Concept ................................ ................................ ................................ ....................... 10 
2.1 SafeContext Is One Part of a Whole ................................ ................................  10 
2.2 Safety Goal ................................ ................................ ................................ ...... 10 
2.3 Safety Requirements ................................ ................................ ....................... 10 
2.4 SafeContext Functionality ................................ ................................ ................ 11 
2.4.1 Safety Part ................................ ................................ ....................... 13 
2.4.2 Detailed List of Functionality ................................ ............................ 15 
2.4.2.1 Safety ................................ ................................ ............ 15 
2.4.2.2 Silent ................................ ................................ ............. 16 
2.4.2.3 Not provided ................................ ................................ .. 17 
2.5 Safe State ................................ ................................ ................................ ........ 19 
3 Overview of Requirements to the OS User ................................ ...............................  20 
4 General SafeContext Assumptions ................................ ................................ ........... 22 
4.1 Context Definition................................ ................................ ............................. 23 
5 OS Source Checksum ................................ ................................ ................................  24 
6 Patching the Configuration Block ................................ ................................ ............. 26 
6.1 Using ElfConverter ................................ ................................ ........................... 26 
6.2 Using ConfigBlockCRCPatch ................................ ................................ ........... 27 
7 General Configuration Guidelines ................................ ................................ ............. 28 
8 Review General Part of Configuration Block ................................ ............................ 30 
8.1 How to Read Back the Configuration ................................ ...............................  30 
8.1.1 Using HexConverter ................................ ................................ ......... 31 
8.1.2 Using ConfigViewer ................................ ................................ .......... 31 
8.2 General Configuration Information ................................ ................................ ... 32 
9 Review Generated Code ................................ ................................ ............................. 33 
9.1 Manual Reviews ................................ ................................ ..............................  33 
9.1.1 Review generated file tcb.h ................................ ..............................  33

--- Page 6 ---
Safety Manual MICROSAR OS SafeContext 
2015, Vector Informatik GmbH Version: 1.05              6 / 80 
10 Qualifying Silent OS Part ................................ ................................ ........................... 34 
10.1 Using MICROSAR Safe Silence Verifier (MSSV) ................................ ............. 34 
11 Review User Software ................................ ................................ ................................  36 
12 Hardware Specific Part ................................ ................................ ...............................  39 
12.1 Interrupt Vector Table ................................ ................................ ....................... 42 
12.1.1 Header Include Section ................................ ................................ .... 42 
12.1.2 Core Exception Vector Table ................................ ............................ 43 
12.1.3 EIINT Vector Table ................................ ................................ ........... 44 
12.1.4 CAT2 ISR Wrappers ................................ ................................ ......... 45 
12.2 Configuration Block ................................ ................................ .......................... 46 
12.2.1 How to read back the ConfigBlock ................................ ................... 46 
12.2.2 Additional Information ................................ ................................ ...... 47 
12.2.3 How to start the review ................................ ................................ ..... 48 
12.2.3.1 Indexes of applications, task , ISRs, trusted and non-
trusted functions ................................ ............................ 49 
12.2.3.2 Review against User’s Design ................................ ....... 49 
12.2.4 How to review the general information (block 0) ...............................  50 
12.2.5 How to review the task start addresses (block 1) ............................. 52 
12.2.6 How to review the task trusted information (block 2) ........................ 53 
12.2.7 How to review the task preemptive information (block 3) .................. 54 
12.2.8 How to review the task stack start and end addresses (block 4 and 
5) ................................ ................................ ................................ ..... 55 
12.2.9 How to review the task ownership information (block 6) ................... 56 
12.2.10 How to review the category 2 ISR start addresses (block 7) ............. 57 
12.2.11 How to review the CAT2 ISR trusted information (block 8) ............... 58 
12.2.12 How to review the CAT2 ISR nested information (block 9) ............... 59 
12.2.13 How to r

[… 74 further page(s) not extracted …]
