---
title: "Watchdog Interface — S-WdgIf SafetyCase"
description: "Converted Safety Manual / Safety Case from S-WdgIf_SafetyCase.pdf (PDF, 290 KB)."
---

:::note
Converted from `WdgIf/doc/S-WdgIf_SafetyCase.pdf` (Safety Manual / Safety Case; original PDF, about 290 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgIf](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
TTTech Automotive GmbH  
Schoenbrunner Str. 7, A-1040 Vienna, Austria, Tel. + 43 1 585 34 34-0, Fax +43 1 585 34 34-90, office@tttech-automotive.com 
No part of the document may be reproduced or transmitted in any form or by any means, electronic or mechanical, for any purpose, without the written permission of TTTech 
Automotive. Company or product names mentioned in this document may be trademarks or registered trademarks of their respective companies. TTTech Automotive undertakes no 
further obligation in relation to this document. 
Copyright © 2010, TTTech Automotive GmbH. All rights reserved.                                                                                                                              Subject to changes and corrections 
Ensuring Reliable Networks 
 
Safe Watchdog Interface 
Safety Case 
  
Author: TTTech 
Reviewer(s): PPU 
Reference: D-SAFEX-IN-70-002 
Security: Confidential 
Version: 1.2.0 
Date: 2014-11-20 
Status: Released

--- Page 2 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-002 Page 2 
Last Change: 2014-11-20 Author: TTTech Version: 1.2.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
 
 
 
Revision Chart 
A revision is a new edition of the document and affects all sections of this document. 
 
Version  Date Responsible Person Modification 
0.1.0 2012-07-02 PPU Creation 
0.2.0 2012-07-19 PPU Corrected ISO/DIS -> ISO 
0.3.0 2012-09-27 PPU Added S-WdgM Stack chapter 
0.4.0 2012-10-01 PPU Versions of artefacts updated 
1.0.0 2012-10-01 PPU Version of this document updated 
1.0.1 2012-10-03 PPU Document derived from common 
Safety Case document ver. 1.0.0. It contains 
now the S-WdgIf unit only. 
Content against 1.0.0 not changed. 
1.0.2 2012-10-04 PPU In the chapter 2 the RAD reference removed 
and the provided ISO lifecycles added. 
1.0.3 2012-11-16 PPU Update of the collected document versions. 
1.0.4 2012-11-19 PPU Update after issue50199. 
1.0.5 2013-01-11 PPU Update after second TÜV assessment 
1.1.0 2014-07-28 VLE Update of the collected document versions 
(issue65369) 
1.1.1 2014-08-13 VLE Update after PPU review. 
1.2.0 2014-11-20 VLE Update of the collected document versions 
(issue69469)

--- Page 3 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-002 Page 3 
Last Change: 2014-11-20 Author: TTTech Version: 1.2.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
Contents 
1 Purpose of this Document ................................ ................................ ................................ .... 4 
2 Software Safety Lifecycle Documentation................................ ................................ ........... 4 
2.1 Safe Watchdog Interface ................................ ................................ ................................ . 5 
2.1.1 Software Requirements Document (SRD) ................................ ................................ ... 5 
2.1.2 Unit Design Document (UDD) ................................ ................................ ...................... 5 
2.1.3 Source Code ................................ ................................ ................................ ................ 6 
2.1.4 Unit Test Specification (UTS) ................................ ................................ ....................... 6 
2.1.5 Unit Test Report (UTR) ................................ ................................ ................................  6 
2.1.6 Safety Manual (SM) ................................ ................................ ................................ ..... 7 
2.1.7 Event Tree Analysis (ETA) ................................ ................................ ........................... 7 
3 Summary ................................ ................................ ................................ ................................  7 
4 Abbreviations and Glossary ................................ ................................ ................................ . 7 
5 References ................................ ................................ ................................ ............................. 8 
5.1 Documents Available on Request ................................ ................................ .................... 8 
5.2 Other Documents ................................ ................................ ................................ ............ 8

--- Page 4 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-002 Page 4 
Last Change: 2014-11-20 Author: TTTech Version: 1.2.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
1 Purpose of this Document 
This document represents the safety case for the Safe Watchdog Interface unit. The Safe 
Watchdog Interface is a part of the Safe Watchdog Manager Stack.  
 
It references all relevant documents to provide evidence that the software units have been 
developed according to ISO26262 requirements for an ASIL D software unit [ISO]. 
  
2 Software Safety Lifecycle Documentation 
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
 6-8: Software unit design and implementation *) 
 6-9: Software unit testing *) 
 
Supporting processes: 
 8-7 Configuration management 
 8-8 Change management 
 8-9 Verification 
 8-10 Documentation 
 8-11 Confidence in the use of software tools 
 
 
*) As far as related to the S-WdgIf as SEooC 
 
Part 6-6 deals with safety requirements, which are always defined on system level. For the 
development of the SEooC, we have made assumptions on the safety requirements, which are 
described in the corresponding SEooC safety manuals. The system integrator must verify that the 
SEooC fits to the actual system safety requirements. 
 
The other software safety lifecycle phases described by ISO26262 have to be executed by the 
system integrator. 
 
The following subsections list the software safety lifecycle artifacts of the software units:

--- Page 5 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-002 Page 5 
Last Change: 2014-11-20 Author: TTTech Version: 1.2.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
 Safety manuals as .pdf files, 
 Source code delivered to customer as pointer to the code location, 
 Requirement, design documentation, and test specification as references to the respective 
documents in the MKS repository. They are identified by MKS document id and the document 
version number, 
 Test results as .doc or .pdf files  
The customer delivery contains user manuals, safety manuals and source code. All other artifacts 
can be audited by the customer on request – either on-site in TTTech Vienna development 
location, or via teleconference (e.g. Webex). 
 
The verification and confirmation measures as required by ISO26262 has been executed as 
described in the Software Project Plan.  
 
The evidence for the execution of all verification and confirmation measures as required by 
ISO26262 are version-controlled in the following directory: 
http://tttechsvn.vie.at.tttech.ttt/trunk/projects/certification/sqa/s-wdgm/evidence 
 
The conformity of the development processes of the S-WdgM Stack with ISO 26262 has 
been assessed in a process audit [AUDIT_S-WdgM]. 
 
2.1 Safe Watchdog Interface 
2.1.1 Software Requirements Document (SRD) 
This document describes the software requirements for Safe Watchdog Interface. The SRD 
represents the software unit high-level requirements as required by ISO 26262 – 6, clause 6. 
 
Document Title Safe Watchdog Interface - Software Requirements Document 
Document Version 1.0.8 
Document Number D-SAFEX-S-70-002 
Location MKS 125936 
Label Release_1_26_3 
 
2.1.2 Unit Design Document (UDD) 
The UDD represents the software unit design specification as required by ISO 26262 – 6, clause 8.  
 
Document Title Safe Watchdog Interface - Unit Design Document 
Document Version 1.0.9 
Document Number D-SAFEX-D-70-001 
Location MKS ID 125939 
Label Release_1_26_3

--- Page 6 ---
Document Name: Safety Case Ref.: D-SAFEX-IN-70-002 Page 6 
Last Change: 2014-11-20 Author: TTTech Version: 1.2.0 © TTTech Automotive GmbH 
Ensuring Reliable Networks 
2.1.3 Source Code 
The source code of the software unit is written in the C programming language. 
Title Safe Watchdog Interface - Source Code 
Version 3.3.6 
Location http://tttechsvn.vie.at.tttech.ttt/branches/For_SAFEEXE_SERIES_Release_1
_26_3/SW/msp-watchdog-if 
 
The exact contents of the Source Code and configuration management tags are described in 
[RAD]. 
 
The HIS metrics and the MISRA rule check are performed with the tool QA-C. 
The HIS metrics report can be found in the folders 
http://t

[… 2 further page(s) not extracted …]
