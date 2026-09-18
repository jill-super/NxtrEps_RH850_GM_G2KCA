---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — TechnicalReference GMLANCalibration"
description: "Converted Technical Reference (vendor) from TechnicalReference_GMLANCalibration.pdf (PDF, 161 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/TechnicalReference_GMLANCalibration.pdf` (Technical Reference (vendor); original PDF, about 161 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
GMLAN 3.1 
Technical Reference 
 
Calibration with GENy 
Version 2.01.01 
 
 
 
 
 
 
 
 
 
 
Authors Gunnar Meiss, Markus Schwarz, Jason Wolbers, Heiko 
Hübler, Frank Triem, Marco Pfalzgraf 
Versions: 2.01.01 
Status: Released

--- Page 2 ---
Technical Reference GMLAN 3.1   
2013, Vector Informatik GmbH Version: 2.01.01 
based on template version 2.7 
2 / 24 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Gunnar Meiss 2007-04-13 1.0 Creation 
Gunnar Meiss 2008-01-16 2.0 Added GENy Support 
Markus Schwarz 2009-03-26 2.00.01 Corrected generation rules for 
nmVNMFStartSendCalCnt 
Jason Wolbers 2012-03-27 2.00.02 Added descriptions for 
IlVnRxMessageEnabled, 
IlVnTxMessageEnabled 
Fixed Init Message description 
Heiko Hübler, 
Marco Pfalzgraf, 
Frank Triem 
2012-10-27 2.01.00 Added description for Rx Timeout Time 
Chapter 3 added 
Added descriptions for ‘Sleep Transition Time’, 
‘Supervision Stability Time’, ‘Max No Sleep 
Confirmation’ 
Frank Triem 2013-01-28 2.01.01 ESCAN00064578: Update GMLAN version 
from GMLAN 3.0 to GMLAN 3.1 
Table 1-1  History of the Document 
1.2 Reference Documents 
Index Document 
[1] Vector’s Interaction Layer User Manual 
[2] Vector’s Interaction Layer Technical Reference for GENy 
[3] Vector’s Interaction Layer Technical Reference for GM 
[4] Vector’s Network Management Technical Reference 
Table 1-2  References Documents 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 3 ---
Technical Reference GMLAN 3.1   
2013, Vector Informatik GmbH Version: 2.01.01 
based on template version 2.7 
3 / 24 
Contents 
3.1.1 What is new?................................................................................................... 6 
3.1.2 What has changed? ........................................................................................  6 
3.2.1 What is new?................................................................................................... 6 
3.2.2 What has changed? ........................................................................................  6 
5.1.1 Message Delay Time ....................................................................................... 9 
5.1.2 Minimum Update Time .................................................................................... 9 
5.1.3 Periodic Rate.................................................................................................  10 
5.1.4 Fast Periodic Rate ......................................................................................... 10 
5.1.5 Init Message .................................................................................................. 10 
5.2.1 Rx Timeout Time ........................................................................................... 11 
5.3.1 Initial Transmit Value ..................................................................................... 12 
5.3.1.1 GENy Configuration ...................................................................................... 13 
5.3.1.2 Initial Default Values of Transmit Signals ....................................................... 13 
5.3.1.3 Start and Stop Default Values of Transmit Signals ......................................... 14

--- Page 4 ---
Technical Reference GMLAN 3.1   
2013, Vector Informatik GmbH Version: 2.01.01 
based on template version 2.7 
4 / 24 
Illustrations 
Figure 5-1 Signal layout of the example message .......................................................... 12 
Figure 5-2 GENy configuration of the ‚Tx Signals’ view  with the example message’s 
signals ........................................................................................................... 13 
Figure 6-1 “BusOff Recovery Time” configuration in GENy ............................................. 16 
Figure 6-2 “Init Delay Time” configuration in GENy ......................................................... 17 
Figure 6-3 "Sleep Transition Time" configuration in GENy .............................................. 18 
Figure 6-4 "Supervision Stability Time" configuration in GENy ........................................ 19 
Figure 6-5 "Max No Sleep Confirmation" configuration in GENy ..................................... 20 
 
Tables 
Table 1-1  History of the Document .................................................................................. 2 
Table 1-2  References Documents ................................................................................... 2

--- Page 5 ---
Technical Reference GMLAN 3.1   
2013, Vector Informatik GmbH Version: 2.01.01 
based on template version 2.7 
5 / 24 
2 Introduction 
This document describes the calibration ( post build configuration) parameters of the 
GMLAN Handler that is configured with GENy . It does not describe the process how the 
calibration of the GMLAN Handler is carried out. 
 
 
Please note 
This document is valid for GMLAN 3.1 
 Il_Vector_Gm version 1.01.00 and higher 
 Nm_Gmlan_Gm version 4.03.00 and higher 
Changes to previous module version can be found in chapter 3.

--- Page 6 ---
Technical Reference GMLAN 3.1   
2013, Vector Informatik GmbH Version: 2.01.01 
based on template version 2.7 
6 / 24 
3 Module History 
This chapter describes the calibration implementation of the Vector Interaction Layer and 
Network Management for General Motors in GENy. 
3.1 Il_Vector_Gm Version 1.01.00 
3.1.1 What is new? 
 The Rx Timeout Time for each message is calibrated (chapter 5.2.1). 
3.1.2 What has changed? 
 There are no changes in this version. 
3.2 Nm_Gmlan_Gm Version 4.03.00 
3.2.1 What is new? 
 New calibrateable values for ‘Sleep Transition Time’, ‘Supervision Stability Time’ and 
‘Max No Sleep Confirmation’ (chapters 6.5, 6.6 and 6.7). 
3.2.2 What has changed? 
 There are no changes in this version.

[… 18 further page(s) not extracted …]
