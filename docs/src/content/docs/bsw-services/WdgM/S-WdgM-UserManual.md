---
title: "Watchdog Manager — S-WdgM UserManual"
description: "Converted User Manual / User Guide from S-WdgM_UserManual.pdf (PDF, 3103 KB)."
---

:::note
Converted from `WdgM/doc/S-WdgM_UserManual.pdf` (User Manual / User Guide; original PDF, about 3103 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to WdgM](./)

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
3.3.1
22.05.2014
D-MSP-M-70-001
Version:
Date:
Document number:
Safe Watchdog Manager
User Manual

--- Page 2 ---
Safe Watchdog Manager
© 2011 - 2014 TTTech Automotive GmbH
Document number: D-MSP-M-70-001
Page 2
TTTech Automotive Confidential and Proprietary
Safe Watchdog Manager  3.3.1
Table of Contents
1
Introduction
4
................................................................................................................................... 5
1.1
Architecture Overview
................................................................................................................................... 7
1.2
Use Cases
................................................................................................................................... 8
1.3
Safe Watchdog Manager Stack Content
2
Safe Watchdog Manager (S-WdgM)
9
................................................................................................................................... 10
2.1
File Structure
................................................................................................................................... 13
2.2
Basic Functionality of the S-WdgM
.......................................................................................................................................................... 13
2.2.1    Supervised Entity and Program Flow Supervision 
.......................................................................................................................................................... 15
2.2.2    Deadline Monitoring 
.......................................................................................................................................................... 18
2.2.3    Alive Supervision 
.......................................................................................................................................................... 21
2.2.4    More Details on Checkpoints and Transitions 
.......................................................................................................................................................... 22
2.2.5    Global Transitions 
.......................................................................................................................................................... 24
2.2.6    Global Transitions and Program Flow 
......................................................................................................................................................... 24
Example of an Incorrect Global Transition Split
......................................................................................................................................................... 25
Example of an Incorrect Program Split in the Middle of an Entity
.......................................................................................................................................................... 25
2.2.7    S-WdgM Supervision Cycle 
.......................................................................................................................................................... 27
2.2.8    S-WdgM Stack Fault Reaction Time 
.......................................................................................................................................................... 30
2.2.9    Reset Path and Safe State 
.......................................................................................................................................................... 31
2.2.10    S-WdgM Local Entity State 
.......................................................................................................................................................... 33
2.2.11    S-WdgM Global State 
................................................................................................................................... 33
2.3
Integration in AUTOSAR 3.1 and 4.0 Environments
................................................................................................................................... 34
2.4
Deviations from the AUTOSAR 4.

--- Page 3 ---
3
Safe Watchdog Manager
© 2011 - 2014 TTTech Automotive GmbH
Page
Document number: D-MSP-M-70-001 TTTech Automotive Confidential and Proprietary
Safe Watchdog Manager  3.3.1
3
Integration
94
................................................................................................................................... 94
3.1
Initialization of the S-WdgM
................................................................................................................................... 95
3.2
Memory Sections
................................................................................................................................... 97
3.3
Timing Setup
.......................................................................................................................................................... 100
3.3.1    Deadline Measurement and Tick Counter 
4
Configuration Generation
102
................................................................................................................................... 102
4.1
S-WdgM Configuration Generator
.......................................................................................................................................................... 103
4.1.1    S-WdgM Configuration Verification 
......................................................................................................................................................... 104
Installing the S-WdgM Verifier
................................................................................................................................... 105
4.2
Workflow
................................................................................................................................... 107
4.3
Output Files
................................................................................................................................... 108
4.4
Error Messages
.......................................................................................................................................................... 108
4.4.1    Basic Errors 
.......................................................................................................................................................... 108
4.4.2    Semantic Errors 
5
Appendix
114
................................................................................................................................... 114
5.1
Watchdog Manager Configuration Verifier Requirements
.......................................................................................................................................................... 114
5.1.1    General Remarks 
.......................................................................................................................................................... 114
5.1.2    General Requirements 
.......................................................................................................................................................... 114
5.1.3    Deltas the S-WdgM Verifier Must Detect between the EDF and the Generated Configuration 
.......................................................................................................................................................... 118
5.1.4    Integrity Checks 
.......................................................................................................................................................... 120
5.1.5    Errors To Be Detected by the Verifier to Protect the Embedded Code 
6
Abbreviations
122
7
Glossary
124
8
References
128
9
License Information
129

--- Page 4 ---
Introduction
Page 4
TTTech Automotive Confid

[… 127 further page(s) not extracted …]
