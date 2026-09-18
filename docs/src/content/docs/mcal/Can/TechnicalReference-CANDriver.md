---
title: "Controller Area Network Driver — TechnicalReference CANDriver"
description: "Converted Technical Reference (vendor) from TechnicalReference_CANDriver.pdf (PDF, 1139 KB)."
---

:::note
Converted from `Can/doc/TechnicalReference_CANDriver.pdf` (Technical Reference (vendor); original PDF, about 1139 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Can](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
1 / 149
 
 
 
 
 
 
 
 
 
 
 
Vector CAN Driver 
Technical Reference 
 
Reference Implementation 1.5 
 
 
Version 3.01.01 
 
 
 
 
 
 
 
 
 
 
Authors: H. Honert, K. Emmert 
Version: 3.01.01 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
TechnicalReference Vector CAN Driver  
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
 
 
2 / 149
1 Document Information 
1.1 History 
Author Date Version Remarks 
Hoffmann July, 30th 1997 1.00 Initial draft 
Baudermann, Ebner Aug, 9th 1999 2.00 Reorganization of the document
Hardware related 
documentation removed 
Ebner Nov, 2nd 1999 2.01 Spelling corrections 
Baudermann Nov, 6th 1999 2.02 Restrictions with reentrance 
capability for the following CAN 
Driver functions: CanInit, 
CanReset..., CanSleep, 
CanWakeUp and CAN 
interrupts 
Honert Dec, 14th 1999 2.03 DLC check added 
Ebner Feb, 8th 2000 2.04 Configuration by tool support 
(CANgen) added 
Baudermann, Rein, Honert, 
Brändle 
May, 23th 2000 2.10 Generally reworked 
According to reference 
implementation, version 1.1 
Honert Oct, 31th 2000 2.11 Description of indexed CAN 
Driver added 
Honert Feb, 28th 2001 2.12 Extensions according to 
reference implementation 
version 1.2 
Hardware related 
documentation of HC12 and 
C16x moved to a separate 
document 
Honert Aug, 10th 2001 2.13 Description of API extended 
 Single Receive Channel CAN 
Driver 
 CanCancelTransmit and 
CanCancelMsgTransmit added 
 Access to ErrorCounters added
Honert,  
 
Emmert 
Aug, 20th 2001 2.14 Prototype of UserPrecopy 
corrected 
Spelling corrections 
Modifications for pdf conversion
Emmert Okt, 9th 2001 2.15 Modifications of Figure 4 and 5. 
Honert Mai, 17th 2002 2.16 Function name corrected for 
indexed driver 
Extensions according to

--- Page 3 ---
TechnicalReference Vector CAN Driver  
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
 
 
3 / 149
reference implementation 
version 1.3 
Ebner, Honert, Emmert Jun, 18th, 2003 2.20 Macro names corrected in 
figure 7. 
Extensions according to 
reference implementation 
version 1.4. 
Additional explanation for offline 
/ partial offline mode (ch. 5.2.6) 
Emmert, Honert Juli, 29th, 2003 2.21 New tables for API descriptions.
Corrections of some 
Parameters and API 
descriptions. 
Stephan Hoffmann, Klaus 
Emmert, Heike Honert, 
Patrick Markl 
May 17nd, 
2004 
2.22 Description of API extended 
 Direct Transmit Objects 
Cancel in Hardware 
Language corrections, New 
Layout, Technical revisions 
Klaus Emmert 
Matthias Fleischmann 
2005-12-30 2.23 GENy added as Generation 
Tool 
Added description for: 
 Multiple ECU 
 Common CAN 
 Signal Access Macros 
 Rx Queue 
 Conditional Message Received 
 Variable Datalen 
Heike Honert 2006-08-01 2.30 Extensions according to 
reference implementation 1.5. 
Heike Honert 2007-01-09 3.00 prepare links to hw specific  
Added description for: 
 CAN RAM check 
 Standard/HighEnd CAN Driver 
Heike Honert 2007-01-29 3.01 some corrections 
 improve Common CAN 
 service functions for conditional 
message reception added 
 Description for Partial Offline 
Mode for GENy modified 
 ESCAN00032527: Update 
description of 
ApplCanAddCanInterruptDisabl
e/Restore call-back function 
Heike Honert 2010-06-11 3.01.01 Reference to documentation of 
VstdLib changed 
Table 1-1  History of the Document

--- Page 4 ---
TechnicalReference Vector CAN Driver  
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
 
 
4 / 149
1.2 Reference Documents 
Index and Document Name 
[1] TechnicalReference_<hardware>.pdf 
Table 1-2  Reference Documents 
 
 
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 5 ---
TechnicalReference Vector CAN Driver  
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
 
 
5 / 149
1.3 Contents 
1 Document Information ............................................................................................... 2 
1.1 History .......................................................................................................... 2 
1.2 Reference Documents ................................................................................. 4 
1.3 Contents....................................................................................................... 5 
2 About this Document ............................................................................................... 13 
2.1 Documents this one refers to….................................................................. 14 
2.2 Naming Conventions.................................................................................. 14 
3 Reference Implementations..................................................................................... 15 
3.1 Version 1.0 ................................................................................................. 15 
3.1.1 What's new?............................................................................................... 15 
3.1.2 What's changed?........................................................................................ 15 
3.2 Version 1.1 ................................................................................................. 16 
3.2.1 What's new?............................................................................................... 16 
3.2.1.1 Mandatory (for all CAN Drivers) ................................................................. 16 
3.2.1.2 Optional (for some specific CAN Drivers) .................................................. 16 
3.2.2 What's changed?........................................................................................ 16 
3.3 Version 1.2 ................................................................................................. 17 
3.3.1 What’s new?...............................................................................................17 
3.3.2 What’s changed? .......................................................................................17 
3.4 Version 1.3 ................................................................................................. 17 
3.4.1 What’s new?...............................................................................................17 
3.4.2 What’s changed? .......................................................................................17 
3.5 Version 1.4 ................................................................................................. 18 
3.5.1 What’s new?...............................................................................................18 
3.5.1.1 Mandatory (for all CAN Drivers) ................................................................. 18 
3.5.1.1.1 Common features....................................................................................... 18 
3.5.1.1.2 Transmission features................................................................................ 18 
3.5.1.2 Optional (for some specific CAN Drivers) .................................................. 18 
3.5.1.2.1 Transmission features................................................................................ 18 
3.5.1.2.2 Reception features ..................................................................................... 18 
3.5.2 What’s changed? .......................................................................................19 
3.5.2.1 Transmission features................................................................................ 19 
3.6 Version 1.5 ................................................................................................. 19 
3.6.1 What’s new?................................................

--- Page 6 ---
TechnicalReference Vector CAN Driver  
©2010, Vector Informatik GmbH Version: 3.01.01 
based on template version 2.1 
 
 
6 / 149
4 Overview ................................................................................................................... 21 
4.1 Short Summary of the Functional Scope ................................................... 22 
4.1.1 Initialization ................................................................................................ 22 
4.1.2 Transmission.............................................................................................. 22 
4.1.3 Reception................................................................................................... 23 
4.1.4 Bus-Off ....................................................................................................... 23 
4.1.5 Slee

[… 143 further page(s) not extracted …]
