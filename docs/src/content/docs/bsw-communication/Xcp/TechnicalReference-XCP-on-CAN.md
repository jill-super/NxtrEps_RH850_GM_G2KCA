---
title: "Universal Measurement and Calibration Protocol — TechnicalReference XCP on CAN"
description: "Converted Technical Reference (vendor) from TechnicalReference_XCP_on_CAN.pdf (PDF, 349 KB)."
---

:::note
Converted from `Xcp/doc/TechnicalReference_XCP_on_CAN.pdf` (Technical Reference (vendor); original PDF, about 349 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to Xcp](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
XCP on CAN 
Technical Reference 
 
XCP on CAN Transport Layer 
 
 
Version 1.08 
 
 
 
 
 
 
 
 
 
 
Authors: Frank Triem, Sven Hesselmann 
Version: 1.08 
Status: released (in preparation/completed/inspected/released)

--- Page 2 ---
Technical Reference XCP on CAN  
1 Document Information 
1.1 History 
Author Date Version Remarks 
Frank Triem 
Klaus Emmert 
2005-01-03 1.0 ESCAN00010737: Initial draft 
Warning Text added 
Frank Triem 2005-02-28 1.1 ESCAN00011300: Manual configuration 
Frank Triem 2005-06-22 1.2 ESCAN00011772: Support multiple CAN channels 
ESCAN00012311: Support CAN-Driver without 
transmit queue 
Frank Triem 2005-12-19 1.3 Rework due to inspection 
Frank Triem 2006-04-24 1.4 ESCAN00015915: Correct filenames 
Frank Triem 2006-05-30 1.5 ESCAN00016517: Update of table of contents 
Frank Triem 2006-10-26 1.6 ESCAN00017220: Documentation of reentrant 
capability of all functions 
Sven 
Hesselmann 
2007-09-14 1.7 Multiple Identity added 
Sven 
Hesselmann 
2008-03-19 1.07.01 Invalid reference corrected 
Andreas 
Herkommer 
2009-01-14 1.08 ESCAN00031509: Description of how to define 
Messages as Application Messages 
 
1.2 Reference Documents 
Index Document 
[1] XCP -Part 1 – Overview, Version 1.0 of 2003-04-08 
[2] XCP -Part 2- Protocol Layer Specification, Version 1.0 of 2003-04-08 
[3] XCP -Part 5- Example Communication Sequences, Version 1.0 of 2003-04-08 
[4] Technical Reference XCP Protocol Layer, Version 1.0 of 2005-01-17 
[5] Technical Reference CAN Driver, Version 2.21 of 2003-07-29 
[6] AN-AND-1-108 Glossary of CAN Protocol Terminology 
http://www.vector-informatik.de
 
©2009, Vector Informatik GmbH Version: 1.08 
based on template version 1.3 
2/  2 7

--- Page 3 ---
Technical Reference XCP on CAN  
1.3 Abbreviations 
Abbreviations Complete expression 
A2L File Extension for an ASAM 2MC Language File 
AML ASAM 2 Meta Language 
API Application Programming Interface 
ASAM Association for Standardization of Automation and Measuring Systems 
CAN Controller Area Network 
CANape Calibration and Measurement Data Acquisition for Electronic Control Systems
CMD Command 
CTO Command Transfer Object 
DAQ Synchronous Data Acquistion 
DLC Data Length Code ( Number of data bytes of a CAN message ) 
DLL Data link layer 
DTO Data Transfer Object 
ECU Electronic Control Unit 
ID Identifier (of a CAN message) 
Identifier Identifies a CAN message 
ISR Interrupt Service Routine 
MCS Master Calibration System 
Message One or more signals are assigned to each message. 
MRB Multi receive buffer 
MRC Multi receive channel 
OEM Original equipment manufacturer (vehicle manufacturer) 
RES Command Response Packet 
SRB Single receive buffer 
SERV Service Request Packet 
STIM Stimulation 
XCP Universal Measurement and Calibration Protocol 
VI Vector Informatik GmbH 
 
Also refer to [6] for a list of common abbreviations and terms. 
©2009, Vector Informatik GmbH Version: 1.08 
based on template version 1.3 
3/  2 7

--- Page 4 ---
Technical Reference XCP on CAN  
1.4 Naming conventions 
The names of the access functi ons provided by the XCP Transport Layer for CAN always 
start with a prefix that  includes the characters ‘Xcp’. The characters ‘Xcp’ are surrounded 
by an abbreviation which refers to the service or to the layer which requests a XCP 
service. The designation of the main services is listed below: 
Naming conventions 
Xcp… It is mandatory to use all functions beginning with Xcp… 
These services are called by either the data link layer, XCP Protocol Layer or 
the application. 
They are e.g. used for the transmission of messages. 
ApplXcp The functions, starting with ApplXcp… are functions that are provided by the 
application and are called by the XCP Transport Layer for CAN. 
These services are user callback functions that are application specific and 
have to be implemented depending on the application. 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire..
©2009, Vector Informatik GmbH Version: 1.08 
based on template version 1.3 
4/  2 7

--- Page 5 ---
Technical Reference XCP on CAN  
Contents 
 
1 Document Information ............................................................................................... 2 
1.1 History .......................................................................................................... 2 
1.2 Reference Documents ................................................................................. 2 
1.3 Abbreviations ............................................................................................... 3 
1.4 Naming conventions..................................................................................... 4 
2 Overview ..................................................................................................................... 7 
3 Functional Description .............................................................................................. 8 
3.1 Overview of the functional scope ................................................................. 8 
3.2 Reception and transmission of XCP packets ............................................... 8 
3.3 Support of multiple CAN channels ............................................................... 8 
4 Integration into the application................................................................................. 9 
4.1 Files.............................................................................................................. 9 
4.2 Version changes .......................................................................................... 9 
4.3 Integration of XCP on CAN into the application ......................................... 10 
5 Description of the API.............................................................................................. 12 
5.1 Version of the source code ........................................................................ 12 
5.2 XCP Transport Layer for CAN services called by the Protocol Layer ........ 13 
5.2.1 ApplXcpSend: Transmission of XCP Packets............................................ 13 
5.2.2 ApplXcpInit: Initialization of XCP Transport Layer for CAN........................ 13 
5.2.3 ApplXcpBackground: Background task of XCP Transport Layer for 
CAN............................................................................................................ 14 
5.3 XCP Transport Layer for CAN services called by the CAN-Driver ............. 15 
5.3.1 XcpPreCopy: XCP message precopy function........................................... 15 
5.3.2 XcpConfirmation: XCP message confirmation ........................................... 16 
5.4 XCP Protocol Layer services called by the Transport Layer for CAN ........ 16 
5.5 CAN-Driver services called by the Transport Layer for CAN ..................... 16 
6 Configuration of XCP on CAN................................................................................. 17 
6.1 Configuration of XCP on CAN with GENy.................................................. 17 
6.1.1 Main configuration page............................................................................. 18 
6.1.2 Channel configuration page ....................................................................... 19 
6.1.3 Multiple Identity configuration..................................................................... 20 
6.2 Configuration of XCP on CAN with GENy and CANgen ............................ 22 
6.2.1 XCP on CAN uses only one CAN channel................................................. 23 
©2009, Vector Informatik GmbH Version: 1.08 
based on template version 1.3 
5/  2 7

--- Page 6 ---
Technical Reference XCP on CAN  
6.2.2 XCP on CAN uses multiple CAN channels ................................................ 24 
7 Limitations ................................................................................................................ 25 
7.1.1 Variable length of XCP Packets is not supported ...................................... 25 
7.1.2 Assignment of CAN identifiers to DAQ lists is not supported ..................... 25 
7.1.3 Detection of all XCP slaves within a network ............................................. 25 
7.1.4 Channel API ............................................................................................... 25 
7.1.5 Multiple Identity only supported for single channel configuration ............... 25 
8 FAQ............................................................................................................................ 26 
8.1 Transmit queue of CAN-Driver is disabled................................................. 26 
9 Contact ................................................

[… 21 further page(s) not extracted …]
