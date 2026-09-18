---
title: "Operating System — TechnicalReference MICROSAROS RH850"
description: "Converted Technical Reference (vendor) from TechnicalReference_MICROSAROS_RH850.pdf (PDF, 737 KB)."
---

:::note
Converted from `Os/doc/TechnicalReference_MICROSAROS_RH850.pdf` (Technical Reference (vendor); original PDF, about 737 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Os](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
MICROSAR OS RH850 
Technical Reference 
 
 
 
 
  
 
 
 
 
 
 
 
 
 
Authors Senol Cendere, Yohan Humbert 
Version 1.09 
Status Released

--- Page 2 ---
Technical Reference MICROSAR OS RH850 
2015, Vector Informatik GmbH Version: 1.09                2 / 57 
 
Document Information 
History 
Author Date Version Remarks 
S. Cendere 2014-01-21 1.00 Creation 
S. Cendere 2014-02-03 1.01 Release for RH850 SafeContext 
S. Cendere 2014-04-24 1.02 Release for RH850 P1M 
S. Cendere 2014-09-30 1.03 Added error numbers for interrupt consistency checks 
Y . Humbert 2014-10-14 1.04 Update 
Y . Humbert 2015-01-29 1.05 Added ASID support 
Y . Humbert 2015-02-26 1.06 Added D1M, E1L, E1M and F1M 
Y . Humbert 2015-06-10 1.07 Added Multicore chapter 
S. Cendere 2015-06-29 1.08 Added Timing Protection chapter 
S. Cendere 2015-08-20 1.09 Removed core exception attributes 
 
Reference Documents 
Ref. Source Title Version 
[1] AUTOSAR AUTOSAR Operating System Specification 
(downloadable from www.Autosar.org) 
3.0.x 
4.0.x 
4.1.x 
[2] OSEK OSEK/VDX Operating System Specification 
(downloadable from www.osek-vdx.org) 
2.2.3 
[3] Vector Informatik GmbH Technical Reference MICROSAR OS 8.00

--- Page 3 ---
Technical Reference MICROSAR OS RH850 
2015, Vector Informatik GmbH Version: 1.09                3 / 57 
 
Scope of the Document 
This technical reference describes the specific use of the MICROSAR OS for Renesas 
RH850. It supplements the general technical reference for MICROSAR OS [3]. 
 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
  
Overview 
This document describes the implementation specific part of the AUTOSAR operating 
system for the Renesas RH850 microcontroller family. In th is document a processor of the 
family may be referred as RH850. 
The common part of all MICROSAR OS implementations is described in document [3]. 
The implementation is based on the OSEK -OS-specification 2.2.3 and on AUTOSAR OS 
specifications 3.0.x/4.0.x/4.1.x. This document assumes that the reader is familiar with  the 
OSEK and AUTOSAR OS specifications. 
OSEK/VDX is a registered trademark of Continental Automotive GmbH (until 2007: 
Siemens AG).

--- Page 4 ---
Technical Reference MICROSAR OS RH850 
2015, Vector Informatik GmbH Version: 1.09                4 / 57 
 
Contents 
1 Overview of MICROSAR OS ................................ ................................ ......................... 8 
1.1 Overview of Properties ................................ ................................ ....................... 8 
2 Installation ................................ ................................ ................................ ..................... 9 
2.1 OIL-Configurator ................................ ................................ ................................  9 
2.1.1 OIL-Implementation Files ................................ ................................ ... 9 
3 Configuration ................................ ................................ ................................ .............. 10 
3.1 XML Configuration ................................ ................................ ........................... 10 
3.2 OIL Configuration ................................ ................................ ............................. 10 
3.3 OS Attributes ................................ ................................ ................................ .... 11 
3.3.1 MpuRegion Sub-Attributes (SC3 and SC4) ................................ ...... 13 
3.3.2 PeripheralRegion Sub-Attributes (SC3 and SC4) ............................. 14 
3.4 Counter Attributes ................................ ................................ ............................ 15 
3.4.1 OSTM Sub-Attributes ................................ ................................ ....... 15 
3.4.2 OSTM_HIRES Sub-Attributes ................................ .......................... 15 
3.5 ISR Attributes ................................ ................................ ................................ ... 16 
3.5.1 ExceptionType Sub-Attributes ................................ .......................... 16 
3.6 Application Attributes ................................ ................................ ....................... 17 
3.6.1 Attribute MpuRegion ................................ ................................ ........ 17 
3.7 Event Attributes ................................ ................................ ................................  18 
3.8 Linker Include Files (SC3 and SC4) ................................ ................................ . 18 
4 System Generation ................................ ................................ ................................ ..... 19 
4.1 Code Generator ................................ ................................ ...............................  20 
5 Stack Handling ................................ ................................ ................................ ............ 21 
5.1 Task Stacks ................................ ................................ ................................ ...... 21 
5.2 ISR Stacks ................................ ................................ ................................ ....... 21 
5.3 System Stack ................................ ................................ ................................ ... 21 
5.4 Startup Stack ................................ ................................ ................................ .... 21 
5.5 Stack Usage Size ................................ ................................ ............................. 21 
5.5.1 Task Stack Usage ................................ ................................ ............ 22 
5.5.2 System Stack Usage ................................ ................................ ........ 22 
5.5.3 ISR Stack Usage ................................ ................................ .............. 22 
6 Interrupt Handling ................................ ................................ ................................ ....... 23 
6.1 Interrupt Vectors ................................ ................................ ..............................  23 
6.1.1 Re

--- Page 5 ---
Technical Reference MICROSAR OS RH850 
2015, Vector Informatik GmbH Version: 1.09                5 / 57 
 
6.1.2 Level Initialization ................................ ................................ ............. 23 
6.2 Interrupt Level and Category ................................ ................................ ............ 24 
6.3 Interrupt Category 1 ................................ ................................ ......................... 24 
6.3.1 Interrupt Processing in C ................................ ................................ .. 24 
6.3.2 Unhandled Exception Determination ................................ ................ 24 
6.4 Interrupt Category 2 ................................ ................................ ......................... 25 
6.4.1 Interrupt Entry ................................ ................................ .................. 25 
6.4.2 Interrupt Exit ................................ ................................ .................... 25 
6.4.3 CAT2 ISR Function ................................ ................................ .......... 25 
6.5 Disabling Interrupts ................................ ................................ .......................... 25 
7 MPU Handling (SC3 and SC4) ................................ ................................ .................... 26 
7.1 MPU Region Usage ................................ ................................ ......................... 26 
7.1.1 MPU Region 0 ................................ ................................ .................. 26 
7.1.2 Static MPU Regions ................................ ................................ ......... 26 
7.1.3 Dynamic MPU Regions ................................ ................................ .... 27 
8 RH850 Peripherals ................................ ................................ ................................ ...... 28 
8.1 Supported System Timer ................................ ................................ .................. 28 
8.2 Supported Time Monitoring Timer ................................ ................................ .... 28 
8.3 Initialization ................................ ................................ ................................ ...... 28 
9 Implementation Specifics ................................ ................................ ........................... 29 
9.1 API Functions ................................ ................................ ......................

[… 51 further page(s) not extracted …]
