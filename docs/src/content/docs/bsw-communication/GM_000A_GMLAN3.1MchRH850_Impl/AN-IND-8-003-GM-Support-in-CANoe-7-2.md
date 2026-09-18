---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — AN-IND-8-003 GM Support in CANoe 7.2"
description: "Converted Portable Document (vendor or generated report) from AN-IND-8-003_GM_Support_in_CANoe_7.2.pdf (PDF, 438 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/AN-IND-8-003_GM_Support_in_CANoe_7.2.pdf` (Portable Document (vendor or generated report); original PDF, about 438 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
GM Support in CANoe 7.2 
Version 2.1 
2010-02-23 
 
Application Note AN-IND-8-003 
 
 
 
Author(s) Siegfried Beeh, Friederike Gengenbach 
Restrictions Customer Confidential: GM worldwide and GM suppliers  
Abstract This application note explains the current stage of GM support in CANoe 7.2 and its 
component Test Feature Set. 
 
Table of Contents 
 
 1  
Copyright © 2010 - Vector Informatik GmbH 
Contact Information:   www.vector.com   or ++49-711-80 670-0 
1.0 Overview ..........................................................................................................................................................2 
1.1 Introduction....................................................................................................................................................2 
1.2 Terms and Abbreviations ..............................................................................................................................2 
2.0 Basic Support in CANoe ..................................................................................................................................3 
2.1 Trace Window ...............................................................................................................................................3 
2.2 Logging..........................................................................................................................................................3 
2.3 Export ............................................................................................................................................................3 
2.4 Interactive Generator Block...........................................................................................................................3 
2.5 Generator Block ............................................................................................................................................3 
2.6 Symbol Selection Dialog ...............................................................................................................................3 
2.7 Data Window .................................................................................................................................................5 
2.8 Graphics Window ..........................................................................................................................................6 
2.9 Panels............................................................................................................................................................6 
2.10 CAPL .............................................................................................................................................................7 
3.0 “GM Package” Modeling Package ...................................................................................................................8 
3.1 Model Generation..........................................................................................................................................8 
3.2 Node Panels, Message Panels .....................................................................................................................8 
3.3 Interaction Layer..........................................................................................................................................10 
3.4 Network Management .................................................................................................................................10 
4.0 Modeling Control Units (ECUs) in CAPL .......................................................................................................11 
4.1 Signal Access..............................................................................................................................................11 
4.2 Receiving Standard Messages .................................................................................................................

--- Page 2 ---
GM Support in CANoe 7.2 
 
   
 
 2 
Application Note AN-IND-8-003 
 
1.0 Overview 
1.1 Introduction 
As a simulation, analysis and testing tool for electronic control units, CANoe supports the GMLAN 3.0 protocol in a 
special way. This document briefly describes the support provided by CANoe specifically for GMLAN and explains 
the possible use cases of the “Test Feature Set” for GMLAN in detail. This document is based on CANoe version 
7.2. Because CANoe support for GMLAN is extended continuously, we recommend that the reader checks whether 
a newer version of this document is available. 
The general Test Feature Set concept is explained in a separate document; see chapter 6.0. Familiarity with the 
Test Featu
re Set is assumed in this document. 
1.2 Terms and Abbreviations 
Term Meaning 
CANoe Vector product 
SUT System under Test 
TFS Test Feature Set 
ÆCANoe component 
TSL Test Service Library 
ÆTFS component 
CAPL CANoe Access Programming Language 
ÆLanguage used for programming simulation 
nodes, test modules etc. in CANoe. 
hsCAN High speed CAN Bus (GM-specific terminology)
swCAN Single wire CAN Bus (GM-specific terminology) 
GM extended 
message 
Message with a 29-bit identifier 
Standard message Message with an 11-bit identifier 
Panel Designer Vector product for editing panels 
Panel Editor Vector product for editing panels 
Test Automation 
Editor 
Vector product for editing XML test modules 
Table 1: Terms and Abbreviations

--- Page 3 ---
GM Support in CANoe 7.2 
 
   
 
 3 
Application Note AN-IND-8-003 
 
2.0 Basic Support in CANoe 
Basic support for GMLAN is activated automatically as soon as a GMLAN network file is identified. The existence 
and contents of the “UseGMParameterIds” network attribute are used as identification criteria. 
Details about basic support, which are available in the Online Help for CANoe, are referenced briefly in the 
following chapters. 
2.1 Trace Window 
Separate columns display GM-specific “SourceID”, “Prio” and “ParameterID” information. The “GMLAN” base 
configuration can be selected. This contains basic information along with additional GM-relevant default columns 
such as “Prio”, “PID”, “SourceID” and “CAN-ID”. 
2.2 Logging 
GM-extended messages are logged along with standard messages. The CAN-ID is decoded in the comment field 
and documented separately as “ParameterID”, “SourceID” and “Prio”. 
2.3 Export 
Signal histories for standard messages can be exported from the log block, but this is not possible for signals on 
GM-extended messages. 
2.4 Interactive Generator Block 
The Interactive Generator Block (IG) allows GM-extended messages to be sent. A special “GMLAN” tab is 
provided for this purpose, as well as the ability to modify the message priority and SourceID. 
 
Figure 1: Defining a message in the Interactive Generator Block 
2.5 Generator Block 
The Generator Block makes it possible to send GM-extended messages in symbolic entry mode. 
2.6 Symbol Selection Dialog 
The symbolic selection dialog makes it possible to select symbols from the network database (*.dbc).

--- Page 4 ---
GM Support in CANoe 7.2 
 
   
 
 4 
Application Note AN-IND-8-003 
 
2.6.1 Selecting a Message 
Messages can be selected, for example, in filters, in the Interactive Generator Block and in the CAPL browser. 
 
Figure 2: Message selection in the symbolic selection dialog 
 
Only the message name is included in the CAPL browser, regardless of the path followed in the selection dialog.

--- Page 5 ---
GM Support in CANoe 7.2 
 
   
 
 5 
Application Note AN-IND-8-003 
 
2.6.2 Selecting a signal 
Signals can be selected, for instance, in the CAPL browser, the Data Window and the Graphics Window. 
 
Figure 3: Signal selection in the symbolic selection dialog  
 
Only the signal name is included in the CAPL browser, regardless of how the selection dialog is navigated. If 
additional qualifiers are required, these can be inserted in the CAPL browser by choosing “Insert message from 
CANdb++…”. 
2.7 Data Window 
Application signals are fully supported in the Data Window.  
. 
  
Figure 4: Data Window

--- Page 6 ---
GM Support in CANoe 7.2 
 
   
 
 6 
Application Note AN-IND-8-003 
 
The send node of the signals can be checked in the special dialog “configuration overview” that is accessible from 
the context menu of the Data Window: 
 
  
Figure 5: Configuration overview 
2.7.1 Special signals in the Data window 
Message-specific statistical signals can be selected in the Data and Graphics windows. These are available for 
standard messages but not for GM-extended messages. 
2.8 Graphics Window 
The Graphics Window allows the display of signals on a timeline. The notes that apply to the Data Window apply 
equally to the selection of signals and special signals in the Graphics Window (see 2.7). 
2.9 Panels 
A panel may contain elements used to visualize and control signal values. The notes that apply to the Data 
Window apply similar to the sele

[… 13 further page(s) not extracted …]
