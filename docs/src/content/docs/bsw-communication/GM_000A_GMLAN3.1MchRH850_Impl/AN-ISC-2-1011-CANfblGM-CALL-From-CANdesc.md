---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — AN-ISC-2-1011 CANfblGM CALL From CANdesc"
description: "Converted Portable Document (vendor or generated report) from AN-ISC-2-1011_CANfblGM_CALL_From_CANdesc.pdf (PDF, 392 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/AN-ISC-2-1011_CANfblGM_CALL_From_CANdesc.pdf` (Portable Document (vendor or generated report); original PDF, about 392 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Calling the GM-Bootloader from CANdesc-Applications 
Version 1.00 
04/05/04 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc 
 
 
 
Author(s)  Armin Happel 
Restrictions  Draft Document 
Abstract  How to call the Vector bootloader from a diagnostic layer built with CANdesc-GM 
 
 
Table of Contents 
 
 
Copyright © 2004 - Vector Informatik GmbH 1 
Contact Information:   www.vector-informatik.de   or +49-711-80670-0 
 
 
 
 
 
1.0 Overview ....................................................................................................................... ................................................... 2 
1.1 Target Group .................................................................................................................................................2 
2.0 Preparing the CDD-File with CANdelaStudio ................................................................................................................... 2 
3.0 Contacts ......................................................................................................................................................................... 11

--- Page 2 ---
Calling the GM-Bootloader from CANdesc-Applications 
Version 1.00 
04/05/04 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc 
 
 
 
Author(s)  Armin Happel 
Restrictions  Draft Document 
Abstract  How to call the Vector bootloader from a diagnostic layer built with CANdesc-GM 
 
 
Table of Contents 
 
 
Copyright © 2004 - Vector Informatik GmbH 2 
Contact Information:   www.vector-informatik.de   or +49-711-80670-0 
 
 
 
 
 
1.0 Overview 
This application note describes how to configure the GM’s CDD-File to prepare a CANdesc-GM to call the Vector 
Flash Bootloader for GM. 
1.1 Target Group 
The target group of this application note are ECU software developers and quality engineers involved in developing 
and testing CAN-based vehicle software. 
2.0 Preparing the CDD-File with CANdelaStudio  
The following snapshots describe how to set-up the CDD-file with CANdelaStudio. 
As a first step, the following services need to be defined: 
 
The picture above shows which services have to be supported to cooperate with a flash download. More 
checkboxes can appear in your configuration.

--- Page 3 ---
Calling the GM-Bootloader from CANdesc-Applications  
 
   
 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc  3
 
 
 
 
 
 
The jump to the bootloader must be configured within the Diagnostic Class “Download”. All other services are 
required to manage the prologue. 
The prologue looks as follows: 
 
FLASH REPROGRAMMING PROLOGUE 
 
 Mandatory requests    Optional requests 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
The application needs to support the services listed above. 
The following pages will show the corresponding pages in CANdelaStudio to define the values: 
 
 
Send Wakeup
Start sending Tester Present
Read Data By Identifier ($1A $B0)
Initiate Diagnostic Operation 
Disable all DTCs ($10 $02) 
Disable Normal Comm ($28)
Report Programmed State ($A2)
Read Data By Identifier ($1A)
Request Programming Mode  
($A5 01 for normal CAN- baudrate or  
$A5 $02 for Hispeed-Mode with SingleWire)
Enable Programming Mode ($A5 $03)
Request Download ($34) 
Security Seed ($27 $xx) 
Security Key ($27 $(xx+1)) 
Functional AllNode requests Physical requests

--- Page 4 ---
Calling the GM-Bootloader from CANdesc-Applications  
 
   
 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc  4
 
 
 
 
 
 
 
The picture above shows the configuration for the service “ReadECUIdentification” ($1A B0). The return value is a 
constant, namely the ECU-Diagnostic Address. Therefore, a generated MainHandler can be configured within the 
property of ReadDataByIdentifier. 
For a full support of the prologue, additional service instances for “ReadDataByIdentifier” need to be implemented. 
These instances must have the DIDs $C1 to $C9 if one or more calibration files need to be supported. This service 
instance reads the software module identifier from the GM-header1 of the application or calibration files. Additional 
service instances that need to be supported are the DIDs $D1 to $D9 to retrieve the alphacode. 
 
                                                      
1 The GM-header must be the section of the downloaded data. It contains the Module checksum, the SWMI and 
DLS-code and some additional information. Refer to GMW3110, section 11 for more information on GM-header.

--- Page 5 ---
Calling the GM-Bootloader from CANdesc-Applications  
 
   
 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc  5
 
 
 
 
 
 
 
This next picture shows how to set-up the the optional service “Initiate Diagnostic Operation”. 
The generated MainHandler-support of CANdesc can be used for this service.

--- Page 6 ---
Calling the GM-Bootloader from CANdesc-Applications  
 
   
 
 
Application Note  AN-ISC-2-1011_CANfblGM_Call_from_CANdesc  6
 
 
 
 
 
 
 
The picture above shows the configuration of the service DisableNormalComm ($28). CANdesc will automatically 
call the NM-Function IlNwmDisableNormalComm(). This function of the GMLAN-NM will automatically shutdown all 
VNs (except VN #0).

[… 5 further page(s) not extracted …]
