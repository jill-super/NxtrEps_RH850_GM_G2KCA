---
title: "Interaction Layer (Signal Communication) — TechnicalReference InteractionLayer GM"
description: "Converted Technical Reference (vendor) from TechnicalReference_InteractionLayer_GM.pdf (PDF, 1095 KB)."
---

:::note
Converted from `Il/doc/TechnicalReference_InteractionLayer_GM.pdf` (Technical Reference (vendor); original PDF, about 1095 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Il](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Interaction Layer for General Motors 
Technical Reference 
 
Il_Vector_Gm with GENy 
Version 2.01.02 
 
 
 
 
 
 
 
 
 
 
 
Authors Ralf Fritz, Gunnar Meiss, Heiko Hübler 
Status Released

--- Page 2 ---
T echnical Reference Interaction Layer for General Motors   
2013, Vector Informatik GmbH Version: 2.01.02 
based on template version 3.6 
2 / 48 
1 Document Information 
This document may be revised and appear in  several versions. The document will be 
classified to permit identification of updates and versions. 
This user manual is related to the source code version (Il_Vector_Gm) 1.01.00 or higher.  
1.1 History 
Author Date Version Remarks 
Ralf Fritz 2003-08-05 1.00 creation 
Ralf Fritz 2004-07-02 1.01 Changed description for ILSetTxMessageEnable 
Ralf Fritz 2004-07-16 1.02 Sample corrected. Restriction added. 
Ralf Fritz 2005-04-27 1.03 Timeout and Source Learning description extended. 
New Layout. 
Ralf Fritz 2005-08-01 1.04 Adaptation of return values of several functions.  
Ralf Fritz 2007-03-29 1.05 Corrected chapter 3.1.2.2 
and 3.1.2.3 
Ralf Fritz 2007-05-01 1.06 Switch to new documentation template. 
Gunnar Meiss 2008-01-17 2.00 Added GENy Support 
Heiko Hübler 2012-10-18 2.01.00 Added Robustness Changes 
Added Clearing Flags on Deactivate VN 
(ESCAN00061059) 
Heiko Hübler 2012-10-26 2.01.01 Changed description of Clearing Flags on Deactivate 
VN 
Heiko Hübler 2013-01-31 2.01.02 Updated GMLAN version (ESCAN00064595) 
improved the description of Source Address Timeout 
Supervision (ESCAN00064519) 
T able 1-1  History of the Document 
1.2 Reference Documents 
No. Source Title V ersion 
[1]  V ector T echnical Reference of V ector’s CAN driver 
(T echnicalReference_CANDriver.pdf). 
2.23.00 
[2]  V ector V ector Interaction Layer T echnical Reference for GENy. 
(T echnicalReference_GENy_InteractionLayer.pdf). 
2.08.00 
[3]  V ector T echnical Reference of V ector’s GMLAN Network Management 
(T echnicalReference_GMLAN_NM.pdf). 
1.07.00 
[4]  OSEK/VDX OSEK/VDX Communication Specification 3.0.3. 3.0.3 
T able 1-2  Reference Documents

--- Page 3 ---
T echnical Reference Interaction Layer for General Motors   
2013, Vector Informatik GmbH Version: 2.01.02 
based on template version 3.6 
3 / 48 
 
Please note 
We have configured the programs in accordance with your specifications in the  
 
 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, V ector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 4 ---
T echnical Reference Interaction Layer for General Motors   
2013, Vector Informatik GmbH Version: 2.01.02 
based on template version 3.6 
4 / 48 
Contents 
1 Document Information ...................................................................................................... 2 
1.1 History .................................................................................................................... 2 
1.2 Reference Documents ........................................................................................... 2 
2 Component History ........................................................................................................... 8 
2.1 Il_Vector_Gm V ersion 1.00.00 ............................................................................... 8 
2.1.1 What is new? ......................................................................................... 8 
2.1.2 What has changed?............................................................................... 8 
2.2 Il_Vector_Gm V ersion 1.01.00 ............................................................................... 8 
2.2.1 What is new? ......................................................................................... 8 
2.2.2 What has changed?............................................................................... 8 
3 Functional Description ..................................................................................................... 9 
3.1 Data Transmission.................................................................................................. 9 
3.1.1 Cyclic Transmission ............................................................................... 9 
3.1.2 Event Based Transmission .................................................................. 10 
3.1.3 Mixed Transmission ............................................................................. 13 
3.2 Signal Access ....................................................................................................... 14 
3.3 Extended CAN Identifiers..................................................................................... 15 
3.3.1 Source Learning .................................................................................. 15 
3.3.2 Source Address Timeout Supervision ................................................. 16 
3.4 Application Controlled Message Filter ................................................................. 17 
3.5 Clearing Flags on Deactivate VN......................................................................... 17 
4 Integration ........................................................................................................................ 18 
4.1 Include structure ................................................................................................... 18 
4.2 Initialization........................................................................................................... 18 
4.3 Cyclic function ...................................................................................................... 19 
5 Configuration ................................................................................................................... 21 
5.1 Database Attributes .............................................................................................. 21 
5.1.1 Send Type ............................................................................................ 21 
5.1.2 Default V alues ...................................................................................... 21 
5.1.3 Tx NCA  Message ................................................................................. 22 
5.1.4 Timeout Supervision ............................................................................ 23 
6 API Description ................................................................................................................ 25 
6.1 Administrative functions ................................

--- Page 5 ---
T echnical Reference Interaction Layer for General Motors   
2013, Vector Informatik GmbH Version: 2.01.02 
based on template version 3.6 
5 / 48 
6.1.1.1 IlInitPowerOn .................................................................... 25 
6.1.1.2 IlInit.................................................................................... 25 
6.1.1.3 IlRxT ask............................................................................. 26 
6.1.1.4 IlTxT ask ............................................................................. 26 
6.1.1.5 IlRxStateT ask .................................................................... 27 
6.1.1.6 IlTxStateT ask..................................................................... 28 
6.1.1.7 IlSetOwnNodeAddress ..................................................... 28 
6.2 Service functions .................................................................................................. 29 
6.2.1.1 IlSetEvent.......................................................................... 29 
6.2.1.2 IlGetNodeCommActiveState............................................. 29 
6.2.1.3 IlSetRxMessageSourceAddress....................................... 30 
6.2.1.4 IlGetRxMessageSourceAddress ...................................... 30 
6.2.1.5 IlSetRxMessageEnable .................................................... 31 
6.2.1.6 IlSetTxMessageEnable..................................................... 31 
6.2.1.7 IlGetTransmitMessageStatus ........................................... 32 
6.3 Callback functions ................................................................................................ 32 
6.3.1 ApplIlSourceAddressLearned.............................................................. 33 
6.3.2 ApplIlRxMsgSrcAddressLearned ........................................................ 33 
6.3.3 ApplIlNodeCommActiveRecovery ....................................................... 34 
6.3.4 ApplIlNodeCommActiveFailed............................................................. 34 
7 Abbreviations................................................................................................................... 36 
8 Appendix .......................................................................................................................... 37 
8.1 Nm_Gmlan_Gm Interface 

[… 42 further page(s) not extracted …]
