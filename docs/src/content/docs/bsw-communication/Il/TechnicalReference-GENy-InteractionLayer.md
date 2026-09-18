---
title: "Interaction Layer (Signal Communication) — TechnicalReference GENy InteractionLayer"
description: "Converted Technical Reference (vendor) from TechnicalReference_GENy_InteractionLayer.pdf (PDF, 2202 KB)."
---

:::note
Converted from `Il/doc/TechnicalReference_GENy_InteractionLayer.pdf` (Technical Reference (vendor); original PDF, about 2202 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Il](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Vector Interaction Layer 
Technical Reference 
 
Il_Vector 
Version 2.10.03 
 
 
 
 
 
 
 
 
 
 
 
Authors Klaus Emmert, Gunnar Meiss, Heiko Hübler 
Status Released

--- Page 2 ---
Technical Reference Vector Interaction Layer   
2013, Vector Informatik GmbH Version: 2.10.03 
based on template version 3.7 
2 / 115 
1 Document Information 
1.1 History 
Author Date Version Remarks 
P . Jost 2000-05-05 1.0 creation 
P . Jost 2000-06-29 1.1 some corrections 
P . Jost 2000-07-13 1.2 changes in Figure 4 and some further corrections 
P . Jost 2000-08-06 1.3 correction of the First-Value Class 
P . Jost 2000-09-13 1.4 little corrections in the description of the TxTask and IlInit 
P . Jost 2001-03-01 1.5 message related transmission modes 
example for timeout monitoring 
multi channel support 
known problems 
integration example 
P . Jost 2001-06-22 1.6 some names of attributes changed 
DataChanged flag 
Tx timeout monitoring 
Rx and Tx default values 
new screen shots of the current Gentool 
changes in the state machine 
and further little corrections 
S. Hoffmann 2001-07-05 1.61 some corrections and branch for an OEM 
P . Jost 2001-07-13 1.62 adapted the corrections of version 1.61 for general IL 
P . Jost 2002-04-05 1.63 Signal groups 
Multiple physical and virtual ECU support 
Multiplex Signals 
Rx timeout monitoring: reload of timer and message 
related notification 
Notification in interrupt and task context (IL Polling) 
IL<Tx/Rx>StateTask 
Attributes for Rx timeout monitoring updated 
Configuration Tool pictures updated 
P . Jost 2002-08-16 1.7 Name of this document changed from User Manual to 
Technical Reference 
Multiple Indication Flags per Signal 
Macro to Get and Clear at once 
Chapter for Configuration Tool updated 
”New Style” API  
Data Type Prefix for Signal Access 
Further Callbacks for State Machine 
Initialization – IlInitPowerOn 
ECU Timeout 
H. Hörner 2003-06-16 1.8 Several wording and spelling issues corrected 
List of abbreviations and glossary removed, replaced by 
an own document 
Implementation details moved to an Annex

--- Page 3 ---
Technical Reference Vector Interaction Layer   
2013, Vector Informatik GmbH Version: 2.10.03 
based on template version 3.7 
3 / 115 
K. Emmert 2003-09-02 1.9 Some design and link modifications. 
H. Hörner 2004-05-14 2.0 Add usage of VStdLib 
Documented return value of flag get macros 
Difference between GenMsgDelayTime and 
GenMsgStartDelayTime clarified 
Some clarifications about signal groups 
Wording enhanced for multiplexed signals 
Klaus Emmert 
Gunnar Meiss 
2005-06-10 2.01 Added support for GENy 
Added new feature dynamic timeout handling 
Added raw API for multiplex signals 
Reworked dbc attributes chapter 
Added matrix with transmission modes 
Gunnar Meiss 
 
2005-08-02 2.02 Adapted GenMsgFastOnStart 
Added GENy Multiplex Support 
Klaus Emmert 
Gunnar Meiss 
2005-11-04 2.03 Added AUTOSAR API for GENy, configuration and signal 
access. 
Added GenMsgFastOnStart for multiplex messages in 
GENy 
Added ESCAN00014120 CANGen 
Added ESCAN00008602 CANGen 
Added ESCAN00008604 CANGen 
Reworked ESCAN00010718 
Gunnar Meiss 2006-02-16 2.04 Added GENy Multiple ECU Reference 
Added ESCAN00013633 
DynRxTimeout API postfix and data types have changed. 
Klaus Emmert 2006-03-13 2.05 Signal Groups for GENy 
Gunnar Meiss 2006-04-06 2.06 Added Indexed API discontinuation for GENy. 
Corrected ApplIlFatalError Prototype 
Improved GenSigTimeoutMsg_<ECU> 
Corrected GenSigSendType description 
Removed GenSigTimeoutMsg_<ECU> for GENy 
Gunnar Meiss 2007-05-16 2.07 Opaque Data Types ESCAN00016935 GENy 
Improved documentation of call contexts of API functions 
ESCAN00017472, ESCAN00018014, ESCAN00014156, 
ESCAN00013962, ESCAN00013423, ESCAN00008047, 
ESCAN00008755 
Gunnar Meiss 2007-12-17 2.08 Added GenSigSuprvResp, GenSigSuprvRespSubValue 
and GenSigTimeoutMsg_<ECU> for GENy 
Updated API descriptions 
Updated GenMsgStartDelayTime 
Updated GenMsgIlSupport 
ESCAN00024092 
Gunnar Meiss 2008-04-21 2.08.01 ESCAN00024091 
Gunnar Meiss 2008-07-17 2.09.00 Reworked Document Structure 
ESCAN00024902 Added Node Mapped dbc Attributes

--- Page 4 ---
Technical Reference Vector Interaction Layer   
2013, Vector Informatik GmbH Version: 2.10.03 
based on template version 3.7 
4 / 115 
Updated Abbreviations and Glossary with CIWI 
ESCAN00028781 Added IlTxRepetitionsAreActive and 
IlTxSignalsAreActive 
ESCAN00028787 Reset Timeout Flags On Release 
Added Geny attribute descriptions 
ESCAN00023799 Added Limitation 
ESCAN00025371 Updated Dynamic Timeout Monitoring 
ESCAN00029109 Added Documentation of Generated 
APIs 
Gunnar Meiss 2008-10-17 2.09.01 ESCAN00030172 The description of IlRxWait() 
is ‎incorrect 
Gunnar Meiss 2011-05-19 2.09.02 ESCAN00049272 OnChangeAndIfActive and 
OnChangeAndIfActiveWithRepetition is described 
incorrect in Table  3-6 "Send Type Matrix" 
ESCAN00049615 Incorrect Enumeration Values of the 
dbc attribute "ILUsed" 
ESCAN00048272 Incorrect Timing Diagram of the 
Transmit Fast if Signal Active Transmission Mode 
Heiko Hübler 2012-03-13 2.10.00 Added Signal status information (UpdateBits) 
Heiko Hübler 2012-05-14 2.10.00 Added description for the GENy GUI attribute “timeout 
time” 
Heiko Hübler 2012-09-13 2.10.01 Added description for PreConfig Switch “Enable  
UpdateBit Support” 
Changed “Send on Init” description  
Heiko Hübler 2012-11-07 2.10.02 ESCAN00041782: One 'e' too much in Technical 
Reference 
ESCAN00062898: Adapted description of Delimitation of 
the Bus Load 
Heiko Hübler 2013-05-13 2.10.03 ESCAN00052197: The OnChange Event is triggered if 
the value for IlPut changes out of the range 
Table 1-1  History of the Document

--- Page 5 ---
Technical Reference Vector Interaction Layer   
2013, Vector Informatik GmbH Version: 2.10.03 
based on template version 3.7 
5 / 115 
1.2 Reference Documents 
No. Source Title Version 
[1]  Vector Vector CAN driver. Technical Reference  
[2]  Vector Vector Multiple ECUs. Technical Reference 1.00.00 
[3]  Vector Vector Configuration Tool. Online Documentation. 
(no printed manual available) 
 
[4]  OSEK OSEK/COM, Version 3.0.3 3.00.03 
[5]   Z.120 (1996). Message Sequence Chart (MSC). 
ITU-T, Geneva 
April.1996 
[6]  Vector Interaction Layer User Manual  
[7]  AUTOSAR AUTOSAR Specification of Module COM 2.0.0 2.00.00 
[8]  AUTOSAR AUTOSAR Specification of Module COM 3.1.0 3.1.0 
Table 1-2  Reference Documents 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 6 ---
Technical Reference Vector Interaction Layer   
2013, Vector Informatik GmbH Version: 2.10.03 
based on template version 3.7 
6 / 115 
Contents 
1 Document Information ................................ ................................ ................................ . 2 
1.1 History ................................ ................................ ................................ ............... 2 
1.2 Reference Documents ................................ ................................ ....................... 5 
2 Introduction................................ ................................ ................................ ................. 11 
2.1 Architecture Overview ................................ ................................ ...................... 12 
2.2 Data Access Concept ................................ ................................ ....................... 13 
2.3 Adapt the Vector Interaction Layer ................................ ................................ ... 15 
3 Functional Description ................................ ................................ ...............................  17 
3.1 Features ................................ ................................ ................................ .......... 17 
3.2 Initialization ................................ ................................ ................................ ...... 17 
3.3 Interaction Layer State Machine ................................ ................................ ....... 18 
3.3.1 States ................................ ................................ ..............................  19 
3.3.1.1 Uninit ................................ ................................ ............. 19 
3.3.1.2 Running ................................ ................................ ......... 19 
3.3.1.3 Waiting ................................ ................................ ........... 19 
3.3.2 State Transitions ................................ ................................ .............. 19 
3.3.2.1 Init ................................ ................................ .................. 19 
3.3.2.2 Start ................................ ..............................

[… 109 further page(s) not extracted …]
