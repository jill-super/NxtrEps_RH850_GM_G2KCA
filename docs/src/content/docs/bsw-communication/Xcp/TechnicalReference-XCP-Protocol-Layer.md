---
title: "Universal Measurement and Calibration Protocol — TechnicalReference XCP Protocol Layer"
description: "Converted Technical Reference (vendor) from TechnicalReference_XCP_Protocol_Layer.pdf (PDF, 986 KB)."
---

:::note
Converted from `Xcp/doc/TechnicalReference_XCP_Protocol_Layer.pdf` (Technical Reference (vendor); original PDF, about 986 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Xcp](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
XCP Protocol Layer 
Technical Reference 
 
 
 
 
Version 1.19.00 
 
 
 
 
 
 
 
 
 
 
Version: 1.19.00 
Status: released

--- Page 2 ---
Technical Reference XCP Protocol Layer  
2015, Vector Informatik GmbH Version: 1.19.00 
 
2 / 105 
1 History 
Date Version Remarks 
2005-01-17 1.00.00 ESCAN00009143: Initial draft 
Warning Text added 
2005-06-22 1.01.00 FAQ extended: ESCAN00012356, ESCAN00012314 
ESCAN00012617: Add service to retrieve XCP state 
2005-12-20 1.02.00 ESCAN00013883: Revise Resume Mode 
2006-03-09 1.03.00 ESCAN00015608: Support command TRANSPORT_LAYER_CMD 
ESCAN00015609: Support XCP on FlexRay Transport Layer 
2006-04-24 1.04.00 ESCAN00015913: Correct filenames 
Data page banking support of application callback template added 
2006-05-08 1.05.00 ESCAN00016263: Describe support of reflected CRC16 CCITT 
ESCAN00016159: Add demo disclaimer to XCP Basic 
2006-05-29 1.06.00 ESCAN00016226: Support XCP on LIN Transport Layer 
2006-07-20 1.07.00 ESCAN00012636: Add configuration with GENy 
ESCAN00016956: Support AUTOSAR CRC module 
2006-10-26 1.08.00 ESCAN00018115: DPRAM Support only available in XCP Basic 
ESCAN00017948: Add paging support 
ESCAN00017221: Documentation of reentrant capability of all 
functions 
2007-01-18 1.09.00 ESCAN00018809: Support data paging on Star12X / Cosmic 
2007-05-07 1.10.00 Description of new features added 
2007-09-14 1.11.00 Segment freeze mode now supported 
2008-07-23 1.12.00 ESCAN00028586: Support of Program_Start callback 
ESCAN00017955: Support MIN_ST_PGM 
ESCAN00017952: Open Interface for command processing 
2008-09-10 1.13.00 Additional pending return value of call backs added 
MIN_ST configuration added 
2008-12-01 1.14.00 ESCAN00018157: SERV_RESET is not supported 
ESCAN00032344: Update of XCP Basic Limitations 
2009-05-14 1.15.00 ESCAN00033909: New features implemented: Prog Write Protection, 
Timestamps, Calibration activation 
2009-07-30 1.15.01 Fixed some editorial errors 
2009-11-17 1.15.02 ESCAN00037907: XCP Memory in far RAM 
2009-12-17 1.16.00 Support of a2l export 
2012-02-20 1.16.01 ESCAN00055216: DAQ Lists can be extended after 
START_STOP_SYNCH 
2012-08-13 1.17.00 ESCAN00060779: Support for address doubling in XCP for DSP 
micros 
2013-06-18 1.17.01 ESCAN00068051: Provide an API to detect XCP state and usage 
2013-12-10 1.18.00 ESCAN00072503 Support custom CRC Cbk

--- Page 3 ---
Technical Reference XCP Protocol Layer  
2015, Vector Informatik GmbH Version: 1.19.00 
 
3 / 105 
ESCAN00072505 Support Generic GET_ID 
2015-03-26 1.19.00 ESCAN00082098 Time Check for DAQ lists 
ESCAN00081839 Wrong prototype description for 
ApplXcpCheckReadAccess 
 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
 
 
Note for XCP Basic 
Please note, that the demo and example programs only show special aspects of the 
software. With regard to the fact that these programs are meant for demonstration 
purposes only, Vector Informatik’s liability shall be expressly excluded in cases of 
ordinary negligence, to the extent admissible by law or statute.

--- Page 4 ---
Technical Reference XCP Protocol Layer  
2015, Vector Informatik GmbH Version: 1.19.00 
 
4 / 105 
Contents 
1 History ................................ ................................ ................................ ........................... 2 
2 Overview ................................ ................................ ................................ ..................... 10 
2.1 Abbreviations and Items used in this paper ................................ ...................... 10 
2.2 Naming Conventions ................................ ................................ ........................ 12 
3 Functional Description ................................ ................................ ...............................  13 
3.1 Overview of the Functional Scope ................................ ................................ .... 13 
3.2 Communication Mode Info ................................ ................................ ............... 13 
3.3 Block Transfer Communication Model (XCP Professional only) ....................... 13 
3.4 Slave Device Identification ................................ ................................ ............... 13 
3.4.1 XCP Station Identifier ................................ ................................ ....... 13 
3.4.2 XCP Generic Identification ................................ ...............................  14 
3.5 Seed & Key ................................ ................................ ................................ ...... 14 
3.6 Checksum Calculation ................................ ................................ ..................... 16 
3.6.1 Custom CRC calculation ................................ ................................ .. 16 
3.7 Memory Protection (XCP Professional only) ................................ .................... 16 
3.8 Event Codes ................................ ................................ ................................ .... 16 
3.9 Service Request Messages (XCP Professional only) ................................ ....... 17 
3.10 User Defined Command ................................ ................................ ................... 17 
3.11 Transport Layer Command ................................ ................................ .............. 18 
3.12 Synchronous Data Transfer ................................ ................................ ............. 18 
3.12.1 Synchronous Data Acquisition (DAQ) ................................ ............... 18 
3.12.2 DAQ Timestamp ................................ ................................ ............... 18 
3.12.3 Power-Up Data Transfer (XCP Professional only) ............................ 19 
3.12.4 Data Stimulation (STIM) (XCP Professional only)............................. 19 
3.12.5 Bypassing (XCP Professional only) ................................ .................. 19 
3.12.6 Data Acquisition Plug & Play Mechanisms ................................ ....... 19 
3.12.7 Event Channel Plug & Play Mechanism ................................ ........... 20 
3.12.8 Runtime Supervision of DAQ Measurement ................................ ..... 20 
3.13 The Online Data Calibration Model ................................ ................................ .. 20 
3.13.1 Page Switching ................................ ................................ ................ 20 
3.13.2 Page Switching Plug & Play Mechanism ................................ .......... 21 
3.13.3 Calibration Data Page Copying ................................ ........................ 21 
3.13.4 Freeze Mode Handling ................................ ................................ ..... 21 
3.14 Flash Programming (XCP Professional only) ................................ ................... 21 
3.14.1 Flash Programming by the ECU’s Application ................................ .. 22 
3.14.2 Flash Programming with a Flash Kernel ................................ ........... 22 
3.14.3 Flash Programming Write Protection ........

--- Page 5 ---
Technical Reference XCP Protocol Layer  
2015, Vector Informatik GmbH Version: 1.19.00 
 
5 / 105 
3.15 EEPROM Access (XCP Professional only) ................................ ....................... 23 
3.16 Parameter Check ................................ ................................ ............................. 24 
3.17 Performance Optimizations ................................ ................................ .............. 24 
3.18 Interrupt Locks ................................ ................................ ................................ . 24 
3.19 Accessing internal data ................................ ................................ .................... 24 
3.20 En- / Disabling the XCP module ................................ ................................ ....... 25 
3.21 Support for address doubling in XCP for DSP micros ................................ ....... 25 
4 Integration into the Application ................................ ................................ ................. 27 
4.1 Files of XCP Professional ................................ ................................ ................ 27 
4.2 Files of XCP Basic ................................ ................................ ........................... 27 
4.3 Version changes ................................ ................................ ..............................  28 
4.4 Integration of XCP into the Application ................................ ............................. 28 
4.4.1 Integration of XCP on CAN (XCP Professional only) ........................ 28 
4.4.2 Integration 

[… 99 further page(s) not extracted …]
