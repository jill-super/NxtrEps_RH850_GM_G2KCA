---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — TechnicalReference CANdesc KWP GM"
description: "Converted Technical Reference (vendor) from TechnicalReference_CANdesc_KWP_GM.pdf (PDF, 946 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/TechnicalReference_CANdesc_KWP_GM.pdf` (Technical Reference (vendor); original PDF, about 946 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
1 / 77 
 
 
 
 
 
 
 
 
 
 
 
CANdesc 
Technical Reference 
 
GM / Opel specifics 
Version 3.2.0 
 
 
 
 
 
 
 
 
 
 
Authors Mishel Shishmanyan; Christoph Rätz; Oliver Garnatz; 
Matthias Heil; Katrin Thurow; Vitalij Krieger; Patrick 
Rieder 
Status Released

--- Page 2 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
2 / 77 
Document Information 
History 
Author Date Version Remarks 
Mishel Shishmanyan 2002-05-07 0.9.0 Creation 
Christoph Rätz 2002-07-31 0.9.4 Reworked and released 
Mishel Shishmanyan 2002-12-12 1.0.0 Added requirements for 
ProgrammingMode (Sid $A5) 
and DeviceControl(Sid $AE) 
Released 
Mishel Shishmanyan 2003-04-09 1.1.0 Added default CANdelaStudio 
attribute settings for 
GM/OPEL ECUs 
Oliver Garnatz 2003-12-19 2.0.0 Adapted to CANdesc 2.xx.xx 
New Word template used. 
Oliver Garnatz 2004-05-14 2.1.0 Replaced AppDesc with 
ApplDesc 
Changed support level of 
‘Security access’ 
Oliver Garnatz, Mishel 
Shishmanyan 
2004-07-15 2.2.0 Added description of 
CANdesc OBD support 
Mishel Shishmanyan 2006-05-02 2.3.0 Added: 
- Service 
DynamicallyDefineMe
ssage ($2C) 
- Service 
DefinePIDByAddress 
($2D) 
- The PacketHandler 
(another type of 
service processor) 
Modified: 
- Cosmetics 
- All APIs described in 
detailed table form 
Removed: 
- None 
Jason Wolbers 2006-08-03 2.4.0 Improved wording 
Mishel Shishmanyan 2006-10-22 2.5.0 Added: 
- 5.1 “ECU Address 
configuration” 
Mishel Shishmanyan 2006-11-03 2.6.0 Modified: 
 - 6.1.2 “Multi address ECU 
(dynamic addressing)” 
Mishel Shishmanyan 2007-12-14 2.7.0 Modified:

--- Page 3 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
3 / 77 
- 7.3 “Service attributes” 
- 6.6 ”Service 
DisableNormalCommunicatio
n ($28)” 
 
Removed: 
 - 6.1.2 “Multi address ECU 
(dynamic addressing)” – only 
target addresses 0xFE and 
0xFD (for gateways only) are 
accepted by CANdesc. 
Mishel Shishmanyan 2010-12-21 2.8.0 Modified: 
- 5.1 ECU Address 
configuration 
Added: 
- 6.5 Service SecurityAccess 
($27) 
Matthias Heil 2011-04-20 3.0.0 Modified: 
 - Update to new formatting 
 - 6.11 Service 
ProgrammingMode ($A5) 
Added: 
 - 4.3 Update from earlier 
versions 
 - 7.4 State group for the 
Programming Sequence 
Katrin Thurow 2011-12-16 3.1.0 Modified: 
- 5.6.3 High speed 
programming mode state 
Vitalij Krieger, Patrick Rieder 2014-05-15 3.2.0 Added: 
- 5.5.1 Sending the 
unsolicited response from a 
different channel on a 
dynamic TP 
- 6.6.1 Activate a $28 post-
handler for the application 
 
Modified: 
- 6.2 Service 
ReadFailureRecordData 
($12)

--- Page 4 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
4 / 77 
  
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire.

--- Page 5 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
5 / 77 
Contents 
1 Related documents ................................ ................................ ................................ ..... 10 
2 Overview ................................ ................................ ................................ ..................... 11 
3 CANdesc support by diagnostic service ................................ ................................ .. 12 
4 Important application requirements ................................ ................................ .......... 16 
4.1 Initialization ................................ ................................ ................................ ...... 16 
4.2 DeviceControl ($AE) service requirement ................................ ........................ 17 
4.3 Update from earlier versions ................................ ................................ ............ 17 
5 GM/Opel specific functionality ................................ ................................ ................... 18 
5.1 ECU Address configuration ................................ ................................ .............. 18 
5.1.1 Gateway ECUs ................................ ................................ ................ 18 
5.1.2 Virtual network management ................................ ............................ 18 
5.1.3 Diagnostic activity notification ................................ .......................... 18 
5.2 Request validation ................................ ................................ ........................... 19 
5.3 Timeout events ................................ ................................ ................................  21 
5.3.1 Tester present timeout ................................ ................................ ...... 21 
5.4 Using the extended negative response ................................ ............................ 21 
5.4.1 Sending an extended negative response during service processing 21 
5.4.2 Sending an unsolicited extended negative response ........................ 22 
5.5 Sending an unsolicited single frame response ................................ ................. 23 
5.5.1 Sending the unsolicited response from a different channel on a 
dynamic TP ................................ ................................ ...................... 24 
5.6 GM/Opel CANdesc state machine access ................................ ....................... 24 
5.6.1 Normal communication state ................................ ............................ 25 
5.6.2 Programming mode state ................................ ................................ . 25 
5.6.3 High speed programming mode state ................................ .............. 26 
5.7 The PacketHandler (another type of service processor) ................................ ... 26 
5.7.1 PacketHandler API ................................ ................................ ........... 27 
6 GM/Opel service implementations ................................ ................................ ............ 30 
6.1 Service InitiateDiagnosticOperation ($10) ................................ ........................ 30 
6.1.1 Service DisableAllDTCs ($10 $02) ................................ ................... 30 
6.1.2 Service EnableDTCsDuringDeviceControl ($10 $03) ....................... 30 
6.2 Service ReadFailureRecordData ($12) ................................ ............................ 31 
6.2.1 Service ReadFailureRecordIdentifiers ($12 $01) ..............................  31 
6.2.2 Service ReadFailureRecordParameters ($12 $02) ........................... 32

--- Page 6 ---
Technical Reference CANdesc 
2014, Vector Informatik GmbH Version: 3.2.0 
based on template version 5.1.0 
6 / 77 
6.3 Service ReturnToNormalMode ($20) ................................ ................................  32 
6.4 Service ReadDataByParameterIdentifier ($22) ................................ ................ 33 
6.4.1 Reading a dynamically defined PID (Parameter Identifier) ............... 33 
6.5 Service SecurityAccess ($27) ................................ ................................ .......... 33 
6.6 Service DisableNormalCommunication ($28) ................................ ................... 34 
6.6.1 Activate a $28 post-handler for the application ................................ . 35 
6.7 Service DynamicallyDefineMessage ($2C) ................................ ...................... 35 
6.8 Operations on dynamically definable DPIDs ................................ .................... 36 
6.8.1 Defining a dynamically definable DPID ................................ ............ 36 
6.8.2 Reading a dynamically definable DPID ................................ ............ 37 
6.9 Service DefinePIDByAddress ($2D) ................................ ................................ . 40 
6.10 Operations on dynamically definable PIDs ................................ ....................... 41 
6.10.1 Defining a dynamically definable PID ................................ ............... 41 
6.10.2 Reading a dynamically definable PID ................................ ............... 42 
6.11 Service ProgrammingMode ($A5) ................................ ................................ .... 48 
6.11.1 Allowing programming mode ($A5 $01/$02) ................................ .... 48 
6.11.2 Entering programming mode ($A5 $03) ................................ ........... 49 
6.11.2.1 FBL start on EnterProgrammingMode ($A5 $03) ........... 49 
6.11.2.2 FBL start on RequestDownload ($34) ............................ 50 
6.11.2.3 Concluding programming mode ............

[… 71 further page(s) not extracted …]
