---
title: "Watchdog Manager — S-WdgM Stack SafetyCase"
description: "Converted Safety Manual / Safety Case from S-WdgM_Stack_SafetyCase.pdf (PDF, 335 KB)."
---

:::note
Converted from `WdgM/doc/S-WdgM_Stack_SafetyCase.pdf` (Safety Manual / Safety Case; original PDF, about 335 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgM](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH  
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
No part of the document may be reproduced or transmitted in any form or by any means, electronic or mechanical, for any purpose, without the written permission of TTTech 
Automotive. Company or product names mentioned in this document may be trademarks or registered trademarks of their respective companies. TTTech Automotive undertakes no 
further obligation in relation to this document. 
Copyright © 2010, TTTech Automotive GmbH. All rights reserved.                                                                                                                              Subject to changes and corrections 
Ensuring Reliable Networks 
 
Safe Watchdog Manager Stack 
Safety Case 
  
Author: TTTech 
Reviewer(s): VLE 
Reference: D-SAFEX-IN-70-001 
Security: Confidential 
Version: 1.1.0 
Date: 14.08.2014 
Status: Released

--- Page 2 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-001 Page 2 
Last Change: 14.08.2014 Author: TTTech Version: 1.1.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
 
Revision Chart 
A revision is a new edition of the document and affects all sections of this document. 
 
Version  Date Responsible Person Modification 
0.1.0 2012-07-02 PPU Creation 
0.2.0 2012-07-19 PPU Corrected ISO/DIS -> ISO 
0.3.0 2012-09-27 PPU Added S-WdgM Stack chapter 
0.4.0 2012-10-01 PPU Versions of artefacts updated 
1.0.0 2012-10-01 PPU Version of this document updated 
1.0.1 2012-10-03 PPU Document split to three module dependent 
documents: S-WdgM, S-WdgIf, S-Wdg 
Content against 1.0.0 not changed 
1.0.2 2012-10-04 PPU In the chapter 2 the RAD reference removed 
and the provided ISO lifecycles added. 
1.0.3 2012-11-16 PPU Version of the documents updated. 
1.0.4 2012-11-19 PPU Version of the documents updated. 
1.0.5 2012-11-19 PPU Version of the documents updated. 
1.0.80 2014-03-03 PPU Based on ver. 1.0.4, the Verifier versions 
updated only. 
1.1.0 2014-08-14 PPU Versions of artefacts updated for release 
1.26.1

--- Page 3 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-001 Page 3 
Last Change: 14.08.2014 Author: TTTech Version: 1.1.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
Contents 
1 Purpose of this Document ................................ ................................ ................................ .... 4 
2 Assumptions on S-WdgM Stack as SEooC ................................ ................................ ......... 4 
2.1 Assumptions on scope................................ ................................ ................................ ..... 4 
3 Software Safety Lifecycles ................................ ................................ ................................ ... 4 
4 Software Safety Lifecycle Documentation................................ ................................ ........... 5 
4.1 Safe Watchdog Manager Stack ................................ ................................ ....................... 6 
4.1.1 Software Project Plan (SPP) ................................ ................................ ........................ 6 
4.1.2 Functional Safety Concept (FSC) ................................ ................................ ................ 6 
4.1.3 Technical Safety Requirements (TSR) ................................ ................................ ......... 6 
4.1.4 System Design (SD) ................................ ................................ ................................ .... 7 
4.1.5 Software Requirements Document (SRD) ................................ ................................ ... 7 
4.1.6 Software Architecture Document (SAD) ................................ ................................ ....... 7 
4.1.7 Integration Test Specification (ITS) ................................ ................................ .............. 7 
4.1.8 Integration Test Report (ITR) ................................ ................................ ....................... 8 
4.2 Safe Watchdog Manager ................................ ................................ ................................ . 8 
4.2.1 Software Requirements Document (SRD) ................................ ................................ ... 8 
4.2.2 Unit Design Document (UDD) ................................ ................................ ...................... 8 
4.2.3 Source Code ................................ ................................ ................................ ................ 9 
4.2.4 Unit Test Specification (UTS) ................................ ................................ ....................... 9 
4.2.5 Unit Test Report (UTR) ................................ ................................ ................................  9 
4.2.6 Safety Manual (SM) ................................ ................................ ................................ ..... 9 
4.2.7 Safe Watchdog Manager Verifier ................................ ................................ ............... 10 
4.2.7.1 Software Requirements Document (SRD) ................................ .......................... 10 
4.2.7.2 Source Code ................................ ................................ ................................ ...... 10 
4.2.7.3 Unit Test Specification (UTS) ................................ ................................ ............. 10 
4.2.7.4 Unit Test Report (UTR) ................................ ................................ ...................... 11 
5 Summary ................................ ................................ ................................ ..............................  11 
6 Abbreviations and Glossary ................................ ................................ ...............................  11 
7 References ................................ ................................ ................................ ........................... 11 
7.1 Documents Available on Request ................................ ................................ .................. 11 
7.2 O

--- Page 4 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-001 Page 4 
Last Change: 14.08.2014 Author: TTTech Version: 1.1.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
1 Purpose of this Document 
This document represents the safety case for the Safe Watchdog Manager Stack. In detail it 
covers following areas:  
 Safe Watchdog Manager Stack (the common parts) 
 Safe Watchdog Manager 
 
The other units of the Safe Watchdog Manager Stack – the Safe Watchdog Interface and the 
Safe Watchdog Driver have separate safety case documents. 
 
The safety case references all relevant documents to provide evidence that the software units 
have been developed according to requirements of ISO26262:2011 (see [ISO]) for an ASIL D 
SEooC software component. 
 
The creation of the proof of due diligence document for the whole watchdog safety concept is the 
responsibility of the integrator of the Safe Watchdog Manager Stack (S-WdgM Stack) and is not 
part of this safety case document. 
  
2 Assumptions on S-WdgM Stack as SEooC 
2.1 Assumptions on scope 
According to ISO 26262:2011-10, clause 9.2.4.2, Step 1a, the following assumptions on scope of 
the software component as an SEooC were made: 
 S-WdgM Stack is integrated into an AUTOSAR 4 or compatible software architecture 
 S-WdgM Stack must not unintentionally interfere with other software components 
 S-WdgM Stack expects that the executing hardware is working correctly  
 
3 Software Safety Lifecycles 
The software units represent SEooC units according to ISO26262. The following software safety 
lifecycles were executed as part of the development process of the software units:  
 
Concept phases: 
 3-7 Hazard analysis and risk assessment *) 
 3-8 Functional Safety Concept *) 
 
Product development at the system level: 
 4-6 Technical Safety Concept *) 
 4-7 System Design *) 
 
Product development at the software level: 
 6-5: Initiation of product development at the software level *)

--- Page 5 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-001 Page 5 
Last Change: 14.08.2014 Author: TTTech Version: 1.1.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
 6-8: Software unit design and implementation *) 
 6-9: Software unit testing *) 
 
Supporting processes: 
 8-7 Configuration management 
 8-8 Change management 
 
*) As far as related to the S-WdgM Stack as SEooC 
 
Part 6-6 deals with safety requirements, which are always defined on system level. For the 
development of the SEooC, we have made assumptions on the safety requirements, which are 
described in the corresponding SEooC safety manuals. The system integrator must verify that the 
SEooC fits to the actual system safety requirements. 
 
The other software safety lifecycle phases described by ISO26262 have to be executed by the 
system integrator. 
 
4 Software Safety Lifecy

[… 6 further page(s) not extracted …]
