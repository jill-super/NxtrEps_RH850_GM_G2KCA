---
title: "Transport Protocol (ISO 15765-2) — TechnicalReference TransportProtocolMultiConnection"
description: "Converted Technical Reference (vendor) from TechnicalReference_TransportProtocolMultiConnection.pdf (PDF, 1804 KB)."
---

:::note
Converted from `Tp/doc/TechnicalReference_TransportProtocolMultiConnection.pdf` (Technical Reference (vendor); original PDF, about 1804 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Tp](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
1 / 177 
 
 
 
 
 
 
 
 
 
 
 
Transport Protocol ISO15765-2 
Technical Reference 
 
Single/Multiple Connection 
Version 3.14.00 
 
 
 
 
 
 
 
 
 
 
Authors Oliver Garnatz, Andreas Pick, Peter Herrmann, 
Thomas Dedler 
Status Released

--- Page 2 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
2 / 177 
Document Information 
History 
Author Date Version Remarks 
Rein 1999-06-22 1.0 File created 
Baeuerle 1999-11-02 1.42 Description of connection 
specific timing parameters 
added 
Ebner 2000-07-17 1.51 Single connection version 
removed; documents only 
contains multiple connection 
extensions 
Garnatz 2000-09-19 2.03 Adaptation to new 
MultiConnection TP 
Garnatz 2001-02-09 2.07 Added new functionality  
Garnatz 2001-05-11 2.10 Update new Generation Tool 
versions 
Garnatz 2001-09-14 2.17 General improvement;  
Update to version 2.17 of 
tpmc.c module  
Garnatz 2002-01.24 2.27 SingleConnection version is 
added; Protocol-Overview is 
added 
Garnatz 2002-06-18 2.33 Added restrictions for data 
consistency 
Pick / Garnatz 2002-10-16 2.36 Update: CAN Driver in polling 
mode 
Added: Fast transmission of 
ConsecutiveFrames 
Update: Usage of TransmitCF 
parameter 
Garnatz 2002-11-29 2.37 General rework  
Garnatz 2003-01-16 2.39 Update: 
TpTransmit/CopyToCan/Appl
TpCheckTA 
Garnatz 2004-01-13 2.44 Update: ApplTpCopyToCAN 
Pick 2004-03-01 2.52 Update: Mixed 29-bit ID 
addressing 
TpRxGetCanBuffer 
TpRxSetBufferOverrun 
TpRxGetAddressExtension 
TpTxSetAddressExtension 
Pick 2004-05-14 2.60 Multiple ECUs example 
Restriction on 
TpTxStateTask/TpRxStateTas
k 
Tx/Rx message buffer

--- Page 3 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
3 / 177 
consistency clarification 
Return value of 
ApplTpPreCopyCheck 
Mixed 11-bit ID addressing 
TpTransmit() return values 
Added TpCanChannelInit() 
Added TpRxSetTransmitID() 
Changed 
TpRxSetBufferOverrun 
Changed 
ApplTpTxCopyToCAN 
Changes in chapter ‘How to 
serve Different  
               Connections (only 
dynamic channels)’. 
Pick 2004-12-01 2.68 Added description for GENy 
configuration tool 
(ESCAN00008734).  
Update of API description 
(ESCAN00008314). 
Feature list added 
(ESCAN00008315). 
Prototype parameter 
corrected (ESCAN00009965) 
 
Pick 2005-04-07 2.72.00 Added description for multiple 
addressing systems. 
C++ access to TPMC. 
Pick 2005-07-14 2.73.00 Added description for GENy 
configuration 
Herrmann 2005-07-19 2.73.00 Added new API functions: 
TpRxSetWaitCorrectSN, 
TpTxSetStrictFlowControlChe
ck 
Herrmann 2005-08-11 2.73.00 Added new API functions: 
TpRxSetTimeoutConfirmation
,  
TpTxSetTimeoutConfirmation, 
TpRxSetTimeoutCF, 
TpTxSetTimeoutCF   
Garnatz 2006-01-13 2.80.00 Added deviation to ISO 
15765-2  
Herrmann 2006-02-08 2.82.00 ISO 15765-2 deviations 
elaborated 
Herrmann 2006-03-03 2.86.00 Cleanup (ESCAN15514) 
Herrmann 2006-03-23 2.86.00 ISO 15765-2 deviations 
elaborated 
Herrmann 2006-04-11 2.87.00 General rework after review 
Herrmann 2006-07-03 2.89.00 Added WaitFrame handling.

--- Page 4 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
4 / 177 
Herrmann 2007-02-01 2.90.00 Added OEM feature 
TP_ENABLE_STRICT_DL_C
HECK  
Herrmann 2007-02-23 2.91.00 Added feature 
TP_DISABLE_MF_RECEPTI
ON 
Herrmann 2007-03-14 2.92.00 Added ApplFuncTpPrecopy 
callback description and 
reduced TpRxResetChannel 
API usage to indication point 
in time or after. 
Herrmann 2007-09-20 2.93.00 Completed Multiple ECU 
description (see chapter 
7.3.1). Added TpRxGet-
AddressingFormat / 
AssignedDestination 
description. 
                                                    VERSION 3.xx  
Herrmann 2007-10-15 3.00.00 Added description for new 
TpClass  
“Dispatched<AddressingType>”  
Herrmann 2007-11-20 3.01.00 Cosmetics / Syntax 
Herrmann 2008-01-14 3.02.00 New API: 
TpTxGetTargetAddress 
Herrmann 2008-02-12 3.03.00 Minor corrections within API 
descriptions 
(ApplTpTxErrorIndication, 
TpRxGetCanBuffer) 
Herrmann 2008-04-17, 
 
2008-07-17 
3.04.00 Added description for 
TP_ENBLE_DYN_CHANNEL_TIM
ING. 
Added description for the usage 
of extended identifiers for 
normal addressing as well at 
configuration time as also 
dynamically at runtime 
(TP_USE_EXT_IDS_FOR_NO
RMAL). 
Herrmann 2008-12-10 3.05.00 Added description for 
GenMsgDelay attribute in 
chapter 3.4.1 
Herrmann 2009-01-25 3.07.00 Adapted version number to 
ALM package number (3.06.00 
skipped) 
Herrmann 2009-11-25 3.08.00 Added description for reception 
and transmission without flow 
control frames for dyn. 
(TpRxWithoutFC, 
TpTxWithoutFC) and static

--- Page 5 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
5 / 177 
(TpTxFlowControl, 
TpRxFlowControl 
) Tp classes. 
Herrmann 2010-01-12 3.09.00 Enhanced description for DLC 
checks on the Rx side (see 
2.4.2.5). 
Added API functions for 29-Bit 
ext. Id dynamic handling. 
Heil 2010-11-08 3.10.00 Added more flexibility for DLC 
checks on the Rx side (see 
2.4.2.5) 
Herrmann 2011-01-19 3.11.00 Moved 
TP_MEMORY_MODEL_DATA   
from user config file to GENy  
Herrmann 2011-04-05 3.12 ESCAN00051019: Added new 
(customer specific) pre-compile 
switches:  
TP_ENABLE_IGNORE_FC_RE
S_STMIN,  
TP_ENABLE_IGNORE_FC_OV
FL (see 3.2.3). 
Herrmann 
 
Dedler 
2011-07-11 
 
2011-09-21 
3.13 ESCAN00051019: Added 
support for the dynamic setting 
of  29-bit CAN-IDs (see 
4.2.2.31, 4.2.2.32, 4.2.3.29, 
4.2.3.30). 
Added new pre-compile switch:  
TP_USE_UNEXPECTED_FC_
CANCELATION (see 3.2.3). 
Dedler 2012-04-10 3.13.01 Description of 
TpRxGetCanBuffer modified 
according to ESCAN00057225 
Dedler 2013-04-30 3.14.00 Description for non-standard 
flow control handling updated 
(3.2.3) 
 
Reference Documents 
No. Title 
[1]  /ISO/TF2/:  ISO FDIS 15765-2; Road vehicles — Diagnostics on CAN — Part 2: Network 
layer services; 
Date 2004-07-16 
[2]  /OSEK-COM/:  OSEK/VDX Communication Version 2.1, revision 1 17th June 1998 
[3]  /CANDrv/:  Manual for CAN Driver in used version 
[4]  ISO15765-2:  ISO TC 22/SC 3;  ISO 15765-2:2003(E); Road vehicles — Diagnostics on 
controller area network (CAN) — Part 2: Part 2: Network layer services

--- Page 6 ---
Technical Reference Transport Protocol ISO15765-2 
2013, Vector Informatik GmbH Version: 3.14.00 
based on template version 5.1.0 
6 / 177 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

[… 171 further page(s) not extracted …]
