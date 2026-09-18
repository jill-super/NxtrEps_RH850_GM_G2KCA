---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — UserManual CANoe Model Generator"
description: "Converted User Manual / User Guide from UserManual_CANoe_Model_Generator.pdf (PDF, 1378 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/UserManual_CANoe_Model_Generator.pdf` (User Manual / User Guide; original PDF, about 1378 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
User Manual 
GMLAN Package 
Installation and usage in CANoe 
Version 2.10.0 
English

--- Page 2 ---
Imprint 
 
Vector Informatik GmbH 
Ingersheimer Straße 24 
D-70499 Stuttgart 
 
 
The information and data given in this user manual can be changed without prior notice. No part of this manual may be reproduced in 
any form or by any means without the written permission of the publisher, regardless of which method or which instruments, electronic 
or mechanical, are used. All technical information, drafts, etc. are liable to law of copyright protection. 
 Copyright 2013, Vector Informatik GmbH  
All rights reserved.

--- Page 3 ---
User Manual GMLAN Package  Table of contents 
© Vector Informatik GmbH Version 2.10.0 - I - 
Table of contents 
1 Introduction 3 
1.1 Package Overview 4 
1.2 Reference Documents 4 
1.3 Features 4 
1.4 History 5 
1.5 Releases and Compatibility 5 
1.6 About this User Manual 7 
1.6.1 Access Helps and Conventions 7 
1.6.2 Certification 8 
1.6.3 Warranty 8 
1.6.4 Support 8 
1.6.5 Registered Trademarks 8 
2 Installation and Configuration 9 
2.1 Prerequisites 10 
2.2 Installation 10 
2.3 Update of CANoe 10 
3 Quick Start 11 
3.1 Automatic Generation of the Simulation Model (recommended) 12 
3.1.1 Model Generation by Drag & Drop 12 
3.1.2 Model Generation Wizard 12 
3.1.3 Trouble-shooting 14 
3.1.4 Result of the Automatic Generation 14 
3.2 Database Settings – to be Considered before the Simulation Model can be Operated 15 
3.2.1 Network Attributes 15 
3.2.2 Node Attributes 15 
3.2.3 Message Attributes 16 
3.2.4 Signal Attributes 17 
4 Operate the Simulation Model 19 
4.1 Main Panel 20 
4.2 ActiveX Controls 21 
4.2.1 ActiveX Message Send Control 22 
4.2.2 ActiveX Message Display Control 23 
4.2.3 ActiveX Network Management Control 24 
4.3 Trouble-shooting 25 
4.3.1 Missing VNMF Messages 25 
4.3.2 Nodes with the Same Source ID 25 
5 Interface Specifications 27 
5.1 Interaction Layer (IL) 28 
5.1.1 Interaction Layer Control 28 
5.1.2 Setting Signal Values 29 
5.1.3 Setting Signal Values - Obsolete API Functions 31 
5.1.4 Reading Signals within CAPL 32 
5.1.5 Incomplete Transmission Models and Tests 33

--- Page 4 ---
Table of contents User Manual GMLAN Package 
- II - Version 2.10.0 © Vector Informatik GmbH 
5.1.6 Fault Injection Functions 34 
5.1.7 GM Specific Functions 36 
5.1.8 Error Codes 37 
5.1.9 Definition of Return Codes for the IL 38 
5.1.10 CAPL Call-back Functions 38 
5.1.11 IL States 39 
5.1.12 Write Window Outputs 40 
5.2 Network Management (NM) 40 
6 Restrictions and Deficiencies 41 
6.1 Restrictions 42 
7 Tips and Examples 43 
7.1 Tips 44 
7.2 Examples 47 
8 Index 49

--- Page 5 ---
User Manual GMLAN Package  Introduction 
© Vector Informatik GmbH Version 2.10.0 - 3 - 
1 Introduction 
In this chapter you find the following information: 
1.1 Package Overview  page 4 
1.2 Reference Documents  page 4 
1.3 Features  page 4 
1.4 History  page 5 
1.5 Releases and Compatibility  page 5 
1.6 About this User Manual  page 7 
 Access Helps and Conventions 
 Certification 
 Warranty 
 Support 
 Registered Trademarks

--- Page 6 ---
Introduction User Manual GMLAN Package 
- 4 - Version 2.10.0 © Vector Informatik GmbH 
1.1 Package Overview 
 This document is the enclosing document for the GMLAN specification 3.0 support 
package. 
Components This package contains the following components: 
> CANoe Interaction Layer GMLAN (GMLAN IL “CANoeILNLGM.DLL”) 
> ActiveX message control panel for GM 
> GMLAN Network Management simulation (GMLAN NM “GMLAN02.DLL”)  
> GMLAN ActiveX NM control panel 
> CAPL generator for GM (“CaplGeneratorGMIL.exe”) 
> Model Generation Support 
 
 
Info: This package requires as minimal CANoe version 7.1. 
 
1.2 Reference Documents 
[1] CANoe online help and manual 
[2] Documentation GMLAN NM DLL (CANoe Start Menu – Help) 
[3] Documentation IVLAN NM DLL (CANoe Start Menu – Help) 
 
1.3 Features 
 The CANoe GMLAN Package supports the GMLAN standard within CANoe. It allows 
creating automatically a simulation model using the network database, and it sup -
ports the Interaction Layer and Network Management functionality within the 
simulation. 
 
CANoe IL GMLAN > Provides a signal-oriented interface 
> Controls the transmission of messages dependent to the send types of signals and 
messages. 
> Provides the possibility to send messages on request (using a signal or a 
message as triggering object) 
> Provides a fault injection interface to influence the sending of messages 
 
Network 
Management 
GMLAN 
> The appropriate DLL implements the GMLAN NM protocol that allows nodes that 
are simulated by CANoe to interact with hardware nodes attached to the CAN 
network 
> Handles all network management concerns for GMLAN including "Virtual Net-
works" (VNs) 
 
ActiveX message 
control/GM 
> Displays the message- and signal-related information and establishes possibilities 
to control them

[… 46 further page(s) not extracted …]
