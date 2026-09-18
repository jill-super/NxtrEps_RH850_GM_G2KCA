---
title: "Network Management — TechnicalReference Nm Gmlan Gm"
description: "Converted Technical Reference (vendor) from TechnicalReference_Nm_Gmlan_Gm.pdf (PDF, 840 KB)."
---

:::note
Converted from `Nm/doc/TechnicalReference_Nm_Gmlan_Gm.pdf` (Technical Reference (vendor); original PDF, about 840 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Nm](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Nm_Gmlan_Gm 
Technical Reference 
 
  
Version 2.03.01 
 
 
 
 
 
 
 
 
 
 
 
Authors Marco Pfalzgraf 
Status Released

--- Page 2 ---
Technical Reference Nm_Gmlan_Gm   
2015, Vector Informatik GmbH Version: 2.03.01 
based on template version 3.7 
2 / 59 
1 Document Information 
1.1 History 
Author Date Version Remarks 
M. Radwick 2002-06-14 1.0 creation 
M. Radwick 2002-12-24 1.1 Incorporate comments from Armin 
Happel. 
Added Introduction, Overview and 
Functional sections. 
Klaus Emmert 
Ralf Fritz 
2004-02-23 1.2 New Layout. 
Minor changes. 
Ralf Fritz/ Laura Winder 2004-10-12 1.3 Minor changes in API chapter. 
Ralf Fritz 2005-05-09 1.4 Data types changed 
Ralf Fritz 2005-08-02 1.5 Macros to access the return value of 
IlNwmIsActiveVN added  
Ralf Fritz 2006-10-02 1.6 Changed description of bus-off recovery 
time. 
Ralf Fritz 2007-03-23 1.7 Function description of  
IlNwmGetActiveListVN changed. 
Calibration section removed 
Description of ApplNwmReinitRequest 
corrected. 
Markus Schwarz 2007-12-06 2.00 ESCAN00021184 
added description for GENy 
adapted to new template 
changed order of chapters 
Markus Schwarz 2010-07-16 2.00.01 ESCAN0030766: added chapter 4.5 
Marco Pfalzgraf 2012-08-15 2.01.00 ESCAN00055995, 
ESCAN00055998: 
adapted chapters 6.2 and 6.3.3 
Marco Pfalzgraf 2012-08-31 2.02.00 ESCAN00054683: Corrected code 
example in chapter 5.3.2 ‘Periodic 
tasks’ 
ESCAN00060804: Added chapter 4.11 
Marco Pfalzgraf 2012-10-26 2.02.01 Added chapter 2 
Marco Pfalzgraf 2013-05-15 2.02.02 ESCAN00067275: Adapted description 
of callback ApplNwmReinitRequest 
Marco Pfalzgraf 2015-01-19 2.03.00 ESCAN00080646: Added API 
description for context switch support 
Marco Pfalzgraf 2015-12-18 2.03.01 ESCAN00069542: Adapted description 
about activation of init active VNs 
ESCAN00087111: Added limitation to 
IlNwmTask API description and chapter 
5.3.2.

--- Page 3 ---
Technical Reference Nm_Gmlan_Gm   
2015, Vector Informatik GmbH Version: 2.03.01 
based on template version 3.7 
3 / 59 
Table 1-1  History of the Document 
1.2 Reference Documents 
No. Source Title Version 
[1]  GM Communication Strategy Specification GMW 3104 1.5 
[2]  GM RSM Fault Detection and Mitigation Algorithm - 
[3]  GM RSM GMLAN Handler Robustness Changes V2 - 
[4]  GM RSM GMLAN Handler NM Race Condition Resolution - 
[5]  Vector Technical Reference GMLAN Calibration 2.01.00 
Table 1-2  Reference Documents 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
Technical Reference Nm_Gmlan_Gm   
2015, Vector Informatik GmbH Version: 2.03.01 
based on template version 3.7 
4 / 59 
Contents 
1 Document Information ................................ ................................ ................................ . 2 
1.1 History ................................ ................................ ................................ ............... 2 
1.2 Reference Documents ................................ ................................ ....................... 3 
2 Component History ................................ ................................ ................................ ...... 7 
2.1 Nm_Gmlan_Gm Version 4.02.00 ................................ ................................ ....... 7 
2.1.1 What is new? ................................ ................................ ..................... 7 
2.1.2 What has changed? ................................ ................................ ........... 7 
2.2 Nm_Gmlan_Gm Version 4.03.00 ................................ ................................ ....... 7 
2.2.1 What is new? ................................ ................................ ..................... 7 
2.2.2 What has changed? ................................ ................................ ........... 7 
3 Introduction................................ ................................ ................................ ................... 8 
3.1 Layer Concept ................................ ................................ ................................ ... 9 
3.2 NM Features ................................ ................................ ................................ .... 10 
3.3 VN Concept ................................ ................................ ................................ ..... 11 
4 Functional Description ................................ ................................ ...............................  12 
4.1 NM States ................................ ................................ ................................ ........ 12 
4.2 Normal Operation ................................ ................................ ............................. 13 
4.3 Low Voltage Tolerant Mode ................................ ................................ .............. 14 
4.4 High Load ................................ ................................ ................................ ........ 15 
4.5 HighSpeed Mode ................................ ................................ ............................. 15 
4.6 Normal Communication Halted Mode ................................ ...............................  16 
4.7 Bus Off ................................ ................................ ................................ ............. 16 
4.8 HLVW Failure Handling ................................ ................................ .................... 16 
4.9 VN Activation Failure ................................ ................................ ........................ 17 
4.10 VNMF Message ................................ ................................ ...............................  18 
4.11 Fault Detection and Mitigation Algorithm ................................ .......................... 18 
4.11.1 VN Active Fault ................................ ................................ ................ 19 
4.11.2 Network Active Fault ................................ ................................ ........ 19 
4.11.3 No Sleep Confirmation Fault ................................ ............................ 19 
5 Integration ................................ ................................ ................................ ................... 21 
5.1 Involved Files ................................ ................................ ................................ ... 21 
5.2 Necessary Steps to Integrate the NM in Your Project ................................ ....... 22 
5.3 Necessary Steps to Run the NM ................................ ....................

--- Page 5 ---
Technical Reference Nm_Gmlan_Gm   
2015, Vector Informatik GmbH Version: 2.03.01 
based on template version 3.7 
5 / 59 
5.3.2 Periodic tasks................................ ................................ ................... 23 
5.4 Operating Systems ................................ ................................ .......................... 24 
5.5 Other Aspects ................................ ................................ ................................ .. 24 
6 Configuration ................................ ................................ ................................ .............. 25 
6.1 Concept ................................ ................................ ................................ ........... 25 
6.2 Data base attributes ................................ ................................ ......................... 25 
6.3 GENy ................................ ................................ ................................ ............... 28 
6.3.1 General ................................ ................................ ............................ 28 
6.3.2 System-specific Configuration Options ................................ ............. 29 
6.3.3 Channel-specific Configuration Options ................................ ........... 30 
6.3.4 VN-specific Configuration Options ................................ .................... 31 
7 API Description ................................ ................................ ................................ ........... 32 
7.1 General ................................ ................................ ................................ ............ 32 
7.2 Common Parameter ................................ ................................ ......................... 32 
7.3 Service Functions ................................ ................................ ............................ 33 
7.4 Callback Functions ................................ ................................ ........................... 43 
7.5 Calibration Constants ................................ ................................ ....................... 56 
8 Glossary and Abbreviations ..................

[… 53 further page(s) not extracted …]
