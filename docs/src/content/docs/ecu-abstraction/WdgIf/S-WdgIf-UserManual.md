---
title: "Watchdog Interface — S-WdgIf UserManual"
description: "Converted User Manual / User Guide from S-WdgIf_UserManual.pdf (PDF, 2484 KB)."
---

:::note
Converted from `WdgIf/doc/S-WdgIf_UserManual.pdf` (User Manual / User Guide; original PDF, about 2484 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgIf](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, support@tttech-automotiv e.com
The data in this document may  not be altered or amended without special notif ication f rom TTTech Automotiv e GmbH. TTTech Automotiv e GmbH
undertakes no f urther obligation in relation to this document. The sof tware described in it can only  be used if  the customer is in possession of  a general
license agreement or single license.
Using and copy ing is only  allowed in concurrence with the specif ications stipulated in the contract. Under no circumstances may  any  part of  this
document be copied, reproduced, transmitted, stored in a retriev al sy stem, or translated into another language without written permission of  TTTech
Automotiv e GmbH.
The names and designations used in this document are trademarks or brands belonging to the respectiv e owners.
© 2011 - 2014 TTTech Automotiv e GmbH. All rights reserv ed.                                                                                 Subject to changes and
corrections.
TTTech Automotiv e GmbH Conf idential and Proprietary  Inf ormation
TTTech Automotive GmbH
1.9.4
21.05.2014
D-MSP-M-70-006
Version:
Date:
Document number:
Safe Watchdog Interface
User Manual

--- Page 2 ---
Safe Watchdog Interface
© 2011 - 2014 TTTech Automotive GmbH
Document number: D-MSP-M-70-006
Page 2
TTTech Automotive Confidential and Proprietary
Safe Watchdog Interface 1.9.4
Table of Contents
1
Introduction
3
2
Safe Watchdog Interface
3
................................................................................................................................... 3
2.1
Basic Functionality of the S-WdgIf
................................................................................................................................... 4
2.2
Extensions to the AUTOSAR Watchdog Interface
................................................................................................................................... 5
2.3
Deviations from the AUTOSAR Watchdog Interface
................................................................................................................................... 5
2.4
Integration with Fully AUTOSAR Compliant Drivers
................................................................................................................................... 5
2.5
Configuration Parameters for the S-WdgIf
................................................................................................................................... 7
2.6
Configuring the S-WdgIf in the ECU Description File
................................................................................................................................... 8
2.7
Preprocessor Options
................................................................................................................................... 9
2.8
File Structure
3
API Description
11
................................................................................................................................... 11
3.1
Type Definitions
................................................................................................................................... 12
3.2
S-WdgIf Functions
................................................................................................................................... 15
3.3
Expected Interfaces
4
S-WdgIf Configuration
16
................................................................................................................................... 16
4.1
Link Time Configuration
................................................................................................................................... 16
4.2
S-WdgIf Configuration Generator
................................................................................................................................... 17
4.3
Error Messages
.......................................................................................................................................................... 17
4.3.1    Basic Errors 
.......................................................................................................................................................... 17
4.3.2    Semantic Errors 
5
Abbreviations
19
6
References
20

--- Page 3 ---
3Page
Introduction
TTTech Automotive Confidential and Proprietary
© 2011 - 2014 TTTech Automotive GmbH
Safe Watchdog Interface 1.9.4
Document number: D-MSP-M-70-006
1
Introduction
The Safe Watchdog Interface (S-WdgIf) is a part of the Safe Watchdog  Manager
Stack.
Note: This is a user manual and does not cover safety-related topics. For safety-related
projects  that  need  to  fulfill  ISO  26262  requirements,  refer  to  the  Safe  Watchdog
Interface Safety Manual [5]
.
Note: The <infix> placeholder used in this document stands for the infix part of the
names of the Watchdog driver functions to which the S-WdgIf interfaces. Depending on
the version of the used AUTOSAR environment, the S-WdgIf can consist of the
following:
In AUTOSAR 4.0 compatible environment, the S-WdgIf consists of the vendor ID and
device name strings, where vendo ID is the ID of the vendor of the Watchdog driver
and device name is the name of the configured Watchdog driver device .
In AUTOSAR 3.1 compatible environment, the S-WdgIf consists of the device name
string, where device name is the name of the configured Watchdog driver device 
2
Safe Watchdog Interface
2.1
Basic Functionality of the S-WdgIf
The S-WdgIf was developed according AUTOSAR version 4.0.1 [2]
 and adapted for
the  AUTOSAR  3.1.4  environment  [1]
.  The  S-WdgIf  is  compatible  with  both
AUTOSAR versions, but not fully compliant. For the deviations, see section Deviations
from
 
the
 
AUTOSAR
 
Watchdog
 
Interface
.
The S-WdgIf is designed to be integrated into an AUTOSAR 3.1.4 and 4.0.1 system.
However, it is not restricted to this AUTOSAR version. The software module can also be
integrated into other versions of AUTOSAR and other system software architectures if
the  integration related  requirements  listed  in the  Safe  Watchdog  Interface  Safety
Manual [5]
 are met.
The S-WdgIf provides a standard interface to all the configured watchdog devices. The
Safe Watchdog Manager (S-WdgM) accesses each configured watchdog through its
Device Index.
The  S-WdgIf  is  hardware-independent  and  abstracts  one  or  more  Safe  Watchdog
Driver modules for the S-WdgM. The S-WdgM calls the S-WdgIf with a  device  index
parameter  (DeviceIndex).  It  is  translated  by  the  S-WdgIf  into  a  S-Wdg  driver
instance. If necessary, additional driver parameters are provided.
Figure 1 shows the layered structure of the S-WdgM. The attached watchdog devices
can be internal, external, or both.
20
20
20
5
20

--- Page 4 ---
Safe Watchdog Interface
Page 4
TTTech Automotive Confidential and Proprietary
© 2011 - 2014 TTTech Automotive GmbH
Safe Watchdog Interface 1.9.4
Document number: D-MSP-M-70-006
 
Internal
 
Watchdog
 
device
 
 
Safe Watchdog
 
Manager
 
Safe Watchdog
 
Interface
 
External
 
Watchdog
 
device
 
Hardware
 
Software 
 
Safe Watchdog 
 
Manager user 
API
 
Safe
 
Watchdog
 
Driver
 
2
 
Safe
 
Watchdog
 
Driver
 
1
 
Safe 
Watchdog
 
Manager
 
St
ack
 
Hardware
 
dependent
 
part
 
BSW’s
 
System
 
API
 
Applications
 
Fig. 1: Layered structure of the Safe Watchdog M anager 
2.2
Extensions to the AUTOSAR Watchdog Interface
The S-WdgIf implements and extends the AUTOSAR  Watchdog  Interface module. It
implements the following two interfaces to the Watchdog Driver:
AUTOSAR-compatible interface
oWdg_<infix>_SetTriggerCondition()
oWdg_<infix>_SetMode()
TTTech-compatible interface
oWdg_<infix>_SetTriggerWindow()
oWdg_<infix>_SetMode()
Switching between the two interfaces with the watchdog driver is done by setting  the
parameter  WdgIfUseAutosarDrvApi
 in a  correspoding  way.  For  details,  see
section Integration
 with
 Fully
 AUTOSAR
 Compliant
 Drivers
 and  the  description of
parameter  WdgIfUseAutosarDrvApi
 in  section  Configuration
 Parameters
 for
the
 
S-WdgIf
.
Function  WdgIf_GetTickCounter()  is  an  additional  extension  to  AUTOSAR,
providing  access  to  the  corresponding  S-Wdg  function
Wdg_<infix>_GetTickCounter(),  if  supported  by  the  hardware  and  if  the
configuration  parameter  WdgIfInternalTickCounterRef
 is  set  in  a
correspoding  way.  For  details,  see  the  description  of  parameter
WdgIfInternalTickCounterRef
 in section Configuration
 Parameters
 for
 the
6
5
6
5
7
7

--- Page 5 ---
5Page
Safe Watchdog Interface
TTTech Automotive Confidential and Proprietary
© 2011 - 2014 TTTech Automotive GmbH
Safe Watchdog Interface 1.9.4
Document number: D-MSP-M-70-006
S-WdgIf
.
2.3
Deviations from the AUTOSAR Watchdog Interface
For safety reasons, the S-WdgIf module should not depend on external modules. This is
why  the  AUTOSAR  module  Development  Error  Tracer  (DET) 

[… 15 further page(s) not extracted …]
