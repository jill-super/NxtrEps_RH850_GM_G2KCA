---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — TechnicalReference CANdesc"
description: "Converted Technical Reference (vendor) from TechnicalReference_CANdesc.pdf (PDF, 3246 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/TechnicalReference_CANdesc.pdf` (Technical Reference (vendor); original PDF, about 3246 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
1 / 158 
 
 
 
 
 
 
 
 
 
 
 
CANdesc 
Technical Reference 
 
  
Version 3.09.00 
 
 
 
 
 
 
 
 
 
 
Authors Oliver Garnatz, Mishel Shishmanyan, Stefan Hübner, 
Matthias Heil, Katrin Thurow, Patrick Rieder, Amr 
Elazhary 
Status Released

--- Page 2 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
2 / 158 
1 History 
Author Date Version Remarks 
Oliver Garnatz 2003-11-12 2.00.00 Splitting into separate documents and 
general revision 
Oliver Garnatz 2004-01-13 2.00.01 Added chapter ‘Application interface flow’ 
Updated format template 
Mishel Shishmanyan 2004-03-09 2.01.00 New application callback convention (from 
CANdesc 2.09.00) 
Mishel Shishmanyan 2004-03-29 2.02.00 New APIs: 
DescGetActivityState (from CANdesc 
2.10.00) 
DescSchedulerTask() (from CANdesc 
2.09.00) 
Mishel Shishmanyan 2004-04-26 2.03.00 Added more information and limitations 
about the ring-buffer mechanism (12.6.9 
“Ring Buffer Mechanism”) 
New feature: 
Support for generic user service (from 
CANdesc 2.11.00) 
Force CANdesc to send RCR-RP 
response (from CANdesc 2.11.00) 
Stefan Hübner 2004-07-16 2.03.01 Editorial revision 
Oliver Garnatz 2004-08-12 2.04.00 Added chapter 4.2 ReadDataByIdentifier 
(SID $22) within the Single- and the Multiple 
PID mode is described 
Oliver Garnatz 2004-10-08 2.05.00 ESCAN0000982: Description of MainHandler 
structure is not readable 
ROE transmission unit is described in detail  
Stefan Hübner 
Oliver Garnatz 
2004-10-15 2.06.00 Some additional information are provided  
Peter Herrmann 
Klaus Emmert 
2005-06-22 2.07.00 Added: Service $2C description. 
Added: Warning Text added 
Mishel Shishmanyan 
Oliver Garnatz 
2005-08.03 2.08.00 API added:  
DescStateTask, 
DescTimerTask,  
DescMayCallStateTaskAgain. 
ApplDescFatalError 
API modified:  
DescTask,  
ApplDescCheckSessionTransition,  
DescGetActivityState,  
DescGetStateSession. 
API removed:

--- Page 3 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
3 / 158 
DescSchedulerTask 
Modified description for 
ReadDataByIdentifier with long data and 
negative response in main-handler. 
Oliver Garnatz 2006-03-02 2.09.00 Added: ...prevent the ECU going to sleep 
while diagnostic is active 
Mishel Shishmanyan 2006-03-24 2.10.00 Added: document overview 
Mishel Shishmanyan 2006-04-27 2.11.00 Modified:  
-12.6.13 DynamicallyDefineDataIdentifier  
($2C) (UDS) functions 
-12.6.13.1 DescMayCallStateTaskAgain() 
 
Mishel Shishmanyan 2007-02-22 2.12.00 Added:  
 - 12.6.9.3 “DescRingBufferCancel()” 
 
Matthias Heil 2008-01-03 2.13.00 Added: 
Caution    concerning    user    main  
handler on protocol level l 
Matthias Heil 2008-02-29 2.14.00 Added: 
Handling of read/write memory by address: 
 - 9.5 “Read/Write Memory by Address” 
- 12.6.8.2 
“DescStartMemByAddrRepeatedCall()” 
- 12.6.14 ”Memory Access Callbacks” 
Mishel Shishmanyan 2008-06-06 2.15.00 Removed: 
Chapter “ResponseOnEvent Transmission 
Unit” 
Added: 
 - 12.6.13.3 “Non-volatile memory support” 
Mishel Shishmanyan 2008-11-09 2.16.00 Modified: 
- 12.6.9 and 12.6.9.1: Added limitation for 
UDS and SPRMIB with the ring buffer usage. 
- 13.6 …work with the ring-buffer mechanism 
Added: 
- 12.6.15 Flash Boot Loader Support 
- 13.8 …send a positive response without 
request after FBL flash job  
Mishel Shishmanyan 2009-05-18 2.17.00 Modified: 
12.6.6.1ApplDescCheckSessionTransition() 
Added: 
12.6.6.3DescIsSuppressPosResBitSet () 
Mishel Shishmanyan 2009-08-11 2.18.00 Modified: 
Minor editorial changes 
5.2 Configure Handlers using  
CANdela attributes – added new  
data object attributes

--- Page 4 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
4 / 158 
Added: 
13.9 …enforce CANdesc to use ANSI C 
instead of hardware optimized bit type 
5.1 Configure DBC attributes for diagnostics 
 
Mishel Shishmanyan 2009-09-17 3.00.00 Added: 
6 CANdesc Configuration in GENy 
8 Multi Identity  
12.6.2 Multi Variant Configuration Functions 
Mishel Shishmanyan 2010-01-26 3.01.00 Added: 
7 CANdescBasic Configuration in GENy 
Mishel Shishmanyan 2010-12-21 3.02.00 Modified: 
12.6.14.1 
ApplDescReadMemoryByAddress() 
12.6.14.2 
ApplDescWriteMemoryByAddress() 
12.6.9.2 DescRingBufferWrite() 
Katrin Thurow 2011-08-25 3.03.00 Added: 
8.1 Single Identity Mode 
8.3 Multi Identity Mode 
13.10 …configure Extended Addressing 
13.11 …use Multiple Addressing 
12.6.6.7 DescGetSessionIdOfSessionState 
Modified: 
8  Multi Identity Support 
13.8 …send a positive response without 
request after FBL flash job 
Katrin Thurow 2011-09-19 3.04.00 Added: 
13.12…use “Dynamic Normal Addressing 
Multi TP” with multiple tester 
Modified: 
13.11 …use Multiple Addressing 
Katrin Thurow 2011-11-27 3.05.00 Added:  
12.6.17 “Spontaneous Response” 
transmission 
Modified: 
6.2.1 Global CANdesc Settings 
Patrick Rieder 2013-01-23 3.06.00 Added: 
10 Generic Processing Notifications 
12.6.18 Generic Processing Notifications 
 
Modified: 
6.2.1 Global CANdesc Settings 
12.6.4 Service callback functions 
12.6.9 Ring Buffer Mechanism 
Small fixes

--- Page 5 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
5 / 158 
Patrick Rieder 2013-05-27 3.07.00 Added: 
11 Busy Repeat Responder Support 
Modified: 
13.12 …use “Dynamic Normal Addressing 
Multi TP” with multiple tester 
Patrick Rieder 2014-07-19 3.08.00 Added: 
5.2 Configure the default session state in the 
CDD 
Modified: 
12.6.5 Unknown (User) Service Handling 
- Consistent naming of the Unknown 
Service Handling 
12.6.17.1 
DescSendApplSpontaneousResponse () 
- Correct API name 
- Added missing pre-condition 
- Correct spelling and formatting 
issues 
Patrick Rieder 2014-11-27 3.08.01 Added:  
5.3 Configuration of Mode 0x06 in the CDD 
file  
9.1 ReadDTCInformation (SID $19)  
Modified:  
Table 6-1  
- Setting “Faultmemory Iteration 
Limiter” is dependent on OEM 
Amr Elazhary 2015-07-31 3.09.00 Added: 
9.1 Clear Diagnostic Information (SID $14) 
(UDS2012)  
Modified: 
12.6.6.1 ApplDescCheckSessionTransition() 
- Added new signature, full message 
context, to the callback.

--- Page 6 ---
Technical Reference CANdesc 
2015, Vector Informatik GmbH Version: 3.09.00 
based on template version 5.1.0 
6 / 158 
Contents 
1 History ................................ ................................ ................................ ........................... 2 
2 Introduction................................ ................................ ................................ ................. 12 
3 Documents this one refers to… ................................ ................................ ................. 13 
4 Architecture Overview ................................ ................................ ................................  14 
4.1 CANdesc – Internal processing ................................ ................................ ........ 14 
4.1.1 Diagnostic protocol ................................ ................................ .......... 14 
4.1.2 How does this flow actually work? ................................ .................... 15 
4.2 Application interface flow ................................ ................................ ................. 17 
4.2.1 Session- and CommunicationControl ................................ ............... 17 
5 Advanced Configuration ................................ ................................ ............................ 19 
5.1 Configure DBC attributes for diagnostics ................................ ......................... 19 
5.2 Configure the default session state in the CDD ................................ ................ 19 
5.3 Configuration of Mode 0x06 in the CDD file ................................ ..................... 20 
6 CANdesc Configuration in GENy ................................ ................................ ............... 21 
6.1 Step One – Importing an ECU Diagnostic Description ................................ ..... 21 
6.2 Step Two – ECU Diagnostic Configuration in GENy ................................ ......... 22 
6.2.1 Global CANdesc Settings ................................ ................................ . 23 
6.2.1.1 Generic Processing Notifications (UDS2012) ................. 28 
6.2.2 Service Specific Settings ................................ ................................ .. 29 
6.2.2.1 Generic Service Settings ................................ ............... 29 
6.2.2.2 Predefined (implemented) Services in CANdesc ............ 30 
6.2.2.3 Signal Access Enabled Services ................................ .... 32 
6.2.3 Timing Settings ................................ ................................ ................ 35 
6.2.4 Security Access Settings (UDS2006) ...........

[… 152 further page(s) not extracted …]
