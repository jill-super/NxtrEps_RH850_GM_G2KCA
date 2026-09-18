---
title: "General Motors Local Area Network 3.1 Medium-Speed Handler for RH850 — UserManual CANdesc"
description: "Converted User Manual / User Guide from UserManual_CANdesc.pdf (PDF, 1671 KB)."
---

:::note
Converted from `GM_000A_GMLAN3.1MchRH850_Impl/doc/UserManual_CANdesc.pdf` (User Manual / User Guide; original PDF, about 1671 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to GM_000A_GMLAN3.1MchRH850_Impl](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
User Manual 
CANdesc  
A Step by Step Introduction
Version 1.7 
English

--- Page 2 ---
Impressum 
 
Vector Informatik GmbH 
Ingersheimer Straße 24 
D-70499 Stuttgart 
 
 
The information and data given in this user manual can be changed without prior notice. No part of this manual may be reproduced in 
any form or by any means without the written permission of the publisher, regardless of which method or which instruments, electronic 
or mechanical, are used. All technical information, drafts, etc. are liable to law of copyright protection. 
 © Copyright 2009, Vector Informatik GmbH  
All rights reserved.

--- Page 3 ---
User Manual CANdesc  Manual Information 
Manual History 
Author Date Version Details 
Klaus Emmert 2004-05-10 1.1 Vector symbols included, template 
version 1.8 used (this history 
included), AppDesc… changed to 
ApplDesc due to software 
modifications, description of GENy 
as generation tool added, testing of 
diagnostics layer described with 
CANoe demo configuration, further 
Information about diagnostic buffer 
(linear and ring buffer mechanism) 
and the repeated service call 
feature 
Klaus Emmert 2004-10-15 1.2 Modifications after Review. 
Klaus Emmert 2005-08-12 1.3 Two new functions: 
DescTimerTask(), 
DescStateTask().  
These two functions can be used 
instead of DescTask to handle the 
timers and the application 
separately. 
Klaus Emmert 2006-03-24 1.4 Issues in example code fixed 
Document overview added 
Oliver Garnatz 2007-01-12 1.5 Added description of 
CANdesc_ConnectorCAN GENy 
component 
Klaus Emmert 2008-01-28 1.6 References fixed 
Manuela Scheufele 2009-07-27 1.7 (see section Version 1.7 on page 
66)  
 
 
Reference Documents 
No. Source Title 
[1] Vector Informatik Technical Reference CANdesc 
[2] Vector Informatik Technical Reference CANdescBasic 
  
 
© Vector Informatik GmbH Version 1.7 - 3 -

--- Page 4 ---
Manual Information User Manual CANdesc 
Inhaltsverzeichnis 
1 Manual Information 6  
1.1 About this user manual 7 
1.1.1 Certification 8 
1.1.2 Warranty 8 
1.1.3 Registered trademarks 8  
1.1.4 Errata Sheet of manufacturers 8  
2 Getting Started 9  
2.1 How to use this Manual 10 
3 Basic Information 11 
3.1 An Overall View 12 
3.2 What is Diagnostic 13 
3.3 What happens during Diagnostics? 13  
3.4 What is CANdesc? 14 
3.5 Tools and Files 14 
3.5.1 CANdela Studio, CDDT, CDD 14  
3.5.2 Generation Tool, CDD, DBC 14  
3.5.3 Generation Process with CANbedded Software Components 15  
3.6 What CANdesc does 15 
3.7 Diagnostics – a more detailed View 17  
3.7.1 Basic Nomenclature from the Bottom Up 18  
3.7.2 The same Nomenclature from the Top Down 19  
3.7.3 Where to find this Nomenclature in CANdela Studio 19  
3.7.4 Generic Handling of a Diagnostic Request in the CANdesc Component 21  
3.7.5 User, None, OEM, Generated – what does this mean? 23  
4 A Few STEPS to CANdesc 24 
4.1 STEP What do you need before start? 25  
4.2 Startup Code 25 
4.3 Overview 25 
4.4 STEP Installation 26 
4.5 STEP Configuration with the Generation Tool 26  
4.5.1 Using the Generation Tool CANgen 26  
4.5.2 Using the Generation Tool GENy 27  
4.6 STEP Generating Files 29 
4.6.1 Using Generation Tool CANgen 29  
4.6.2 Using the Generation Tool GENy 32  
4.7 STEP Add CANbedded to your Project 32  
4.8 STEP Adapt Your Application Files 33  
4.8.1 Including, Initializing and Cyclic Calling 33  
4.9 STEP Functional Connection between your Application and CANdesc/CANdela Studio 35  
4.9.1 How to handle User-Defined Handlers 35  
4.9.2 How to Handle Predefined Handlers (for MainHandler only) 38  
4.9.3 Handling OEM-Specific Settings 40  
- 4 - Version 1.7 © Vector Informatik GmbH

--- Page 5 ---
User Manual CANdesc  Manual Information 
4.10 STEP Compile and link your Project 41  
4.11 STEP Test it via CANoe 41  
4.11.1 Start CANoe.CAN OSEK TP enlarged 41  
4.11.2 Test of CANdesc 42  
5 Further Information 44 
5.1 Diagnostic State Handling using CANdela Studio 45  
5.2 Typical Examples of State Groups and States in an Automotive Environment 45  
5.3 Creating and editing State Groups, States and Transitions 45  
5.4 Connection between the states and your application 47  
5.5 Diagnostic Buffer 48 
5.5.1 Linear Diagnostic Buffer 48  
5.5.2 Ring Buffer Mechanism 49  
5.5.2.1 Activation of the Ring Buffer 51  
5.5.2.2 Main Control Functions for the Ring Buffer Mechanism 51  
5.5.2.3 Examples for Ring Buffer Mechanism 52  
5.6 Repeated Service Call Feature 55  
5.6.1 Activation of the Repeated Service Call 55  
5.6.2 Repeated Service Call and Ring Buffer 1 – “Write and Check” 56  
5.6.3 Repeated Service Call and Ring Buffer 2 – “Check and Write” 57  
6 Additional Information 58 
6.1 Persistors 59 
6.1.1 Update Persistors – Install current Version 60  
7 FAQs 63 
7.1 Introduction 64 
7.2 Frequently Asked Questions 64  
8 What’s new, what’s changed 65 
8.1 Version 1.7 66 
8.1.1 What’s new 66 
8.1.2 What’s changed 66  
9 Address table 67 
10 Glossar 69 
11 Index 70 
 
© Vector Informatik GmbH Version 1.7 - 5 -

--- Page 6 ---
Manual Information User Manual CANdesc 
1 Manual Information 
In this chapter you find the following information: 
1.1 About this user manual  page 7
 Certification 
 Warranty 
 Registered trademarks 
 Errata Sheet of manufacturers 
  
 
- 6 - Version 1.7 © Vector Informatik GmbH

[… 66 further page(s) not extracted …]
