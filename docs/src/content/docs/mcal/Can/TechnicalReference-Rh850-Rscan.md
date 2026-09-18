---
title: "Controller Area Network Driver — TechnicalReference Rh850 Rscan"
description: "Converted Technical Reference (vendor) from TechnicalReference_Rh850_Rscan.pdf (PDF, 1103 KB)."
---

:::note
Converted from `Can/doc/TechnicalReference_Rh850_Rscan.pdf` (Technical Reference (vendor); original PDF, about 1103 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Can](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector CAN Driver 
Technical Reference 
 
Renesas 
RH850 
RSCAN 
 
Version 1.08.00 
 
 
 
 
 
 
 
 
 
Authors Torsten Kercher 
Status Released

--- Page 2 ---
Vector CAN Driver Technical Reference RH850 RSCAN  
2015, Vector Informatik GmbH Version: 1.08.00  
based on template version 3.2 
 
2 /50  
Document Information 
History 
 
Author Date Version Remarks 
Torsten Kercher 2013-05-27 1.00.00 Initial release (support F1L with GreenHills compiler) 
Torsten Kercher 2013-07-18 1.01.00 Support R1L derivatives 
Correct description of nested interrupt behavior 
Torsten Kercher 2013-08-26 1.02.00 Support HighEnd features 
Support WindRiver Diab compiler 
Torsten Kercher 2013-10-16 1.03.00 Support R1M derivatives 
Update referenced version of the R1x manual 
Support external wakeup functionality 
Update chapters 5, 6, 7.2.2 
Torsten Kercher 2014-04-04 1.04.00 Support extended CAN RAM check 
Support RSCAN RAM test 
Support D1L, D1M, P1M derivatives 
Update referenced version of the F1L manual 
Torsten Kercher 2014-04-29 1.04.01 Update description of nested interrupt behavior 
Torsten Kercher 2014-05-15 1.05.00 Support IAR compiler 
Support F1H derivatives 
Update expected loop durations in chapter 5 
Torsten Kercher 2014-07-23 1.06.00 Support Renesas compiler 
Support C1H, C1M, E1L, E1M derivatives 
Update chapters 5, 9.4, 10.3 
Update ref. versions of the F1L and F1H manuals 
Torsten Kercher 2014-11-24 1.07.00 Support configuration of the used ‘CAN Interface’ 
Support F1M derivatives 
Update chapters 5, 6, 7.2.9, 9.4, 10.3 
Update ref. versions of the P1x and R1x manuals 
Torsten Kercher 2015-08-19 1.08.00 Support F1K derivatives 
Table 1-1  History of the document 
 
  
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vecto r’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Vector CAN Driver Technical Reference RH850 RSCAN  
2015, Vector Informatik GmbH Version: 1.08.00  
based on template version 3.2 
 
3 /50  
Contents 
 
1 Introduction ................................ ................................ ................................ .................... 5 
2 Important References ................................ ................................ ................................ .... 6 
3 Usage of Controller Features ................................ ................................ ........................ 7 
3.1 [#hw_comObj] - Communication Objects ................................ ......................... 7 
3.2 Acceptance Filters ................................ ................................ ......................... 10 
4 [#hw_sleep] - SleepMode and WakeUp ................................ ................................ ....... 11 
4.1 Sleep ................................ ................................ ................................ ............. 11 
4.2 Internal Wakeup ................................ ................................ ............................ 11 
4.3 External Wakeup ................................ ................................ ........................... 11 
5 [#hw_loop] - Hardware Loop Check ................................ ................................ ............ 13 
6 [#hw_busoff] - Bus off ................................ ................................ ................................ . 16 
7 CAN Driver Features ................................ ................................ ................................ .... 17 
7.1 [#hw_feature] - Feature List ................................ ................................ ........... 17 
7.2 Description of Hardware-related Features ................................ ..................... 19 
7.2.1 [#hw_status] - Status ................................ ................................ ..................... 19 
7.2.2 [#hw_stop] - Stop Mode ................................ ................................ ................ 19 
7.2.3 [#hw_int] - Control of CAN Interrupts ................................ ............................. 19 
7.2.4 [#hw_cancel] - Cancel in Hardware ................................ ...............................  20 
7.2.5 Remote Frames ................................ ................................ ............................ 20 
7.2.6 CAN RAM Check ................................ ................................ .......................... 20 
7.2.7 Extended CAN RAM Check ................................ ................................ ........... 21 
7.2.8 RSCAN ECC Configuration ................................ ................................ ........... 22 
7.2.9 RSCAN RAM Test ................................ ................................ ......................... 23 
8 [#hw_assert] – Assertions ................................ ................................ ........................... 24 
9 API ................................ ................................ ................................ ................................ . 25 
9.1 Category ................................ ................................ ................................ ....... 25 
9.2 RSCAN ECC Configuration ................................ ................................ ........... 25 
9.3 (Extended) CAN RAM Check ................................ ................................ ........ 26 
9.4 External CAN Interrupt Handling ................................ ................................ ... 31

--- Page 4 ---
Vector CAN Driver Technical Reference RH850 RSCAN  
2015, Vector Informatik GmbH Version: 1.08.00  
based on template version 3.2 
 
4 /50  
10 Implementations Hints ................................ ................................ ................................ . 35 
10.1 Important Notes ................................ ................................ ............................. 35 
10.2 Interrupt Configuration ................................ ................................ ................... 36 
10.2.1 Configuration of Interrupt Vectors with IAR compiler................................ ...... 37 
10.3 External CAN Interrupt Handling ................................ ................................ ... 38 
10.3.1 Hardware Access by Call-Back Functions ................................ ..................... 38 
10.3.2 Interrupt Control by Application ................................ ................................ ..... 38 
11 Configuration................................ ................................ ................................ ................ 41 
11.1 Configuration by GENy ................................ ................................ .................. 41 
11.1.1 Platform Settings ................................ ................................ ........................... 41 
11.1.2 Component Settings ................................ ................................ ...................... 42 
11.1.3 Channel-specific Settings ................................ ................................ .............. 43 
11.2 Manual Configuration ................................ ................................ .................... 48 
12 Known Issues / Limitations ................................ ................................ ......................... 49 
13 Contact................................ ................................ ................................ .......................... 50 
 
 
 
Illustrations 
 
 
Figure 3-1 Hardware Object Layout ................................ ................................ ............. 7 
Figure 11-1 GENy Platform Settings ................................ ................................ ............ 41 
Figure 11-2 GENy Component Settings ................................ ................................ ....... 42 
Figure 11-3 GENy Channel Specific Settings ................................ ...............................  43 
Figure 11-4 GENy Acceptance Filter Configuration ................................ ...................... 45 
Figure 11-5 GENy Acceptance Filter Assignment ................................ ........................ 46 
Figure 11-6 GENy Bustiming Configuration ................................ ................................ . 47 
 
 
Tables 
 
Table 1-1  History of the document ................................ ................................ .............. 2 
Table 2-1  Supported Hardware Overview ................................ ................................ ... 6 
Table 3-1  Hardware Object Layout ................................ ................................ ............. 9 
Table 7-1  CAN Driver Functionality ................................ ................................ .......... 18 
Table 7-2  CAN Status ................................ ..........

[… 44 further page(s) not extracted …]
