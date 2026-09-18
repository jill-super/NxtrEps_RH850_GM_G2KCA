---
title: "Limiter Coding — LimrCdng MDD"
description: "Converted Design / Integration Document from LimrCdng_MDD.docx (DOCX, 106 KB)."
---

:::note
Converted from `SF038A_LimrCdng_Impl/doc/LimrCdng_MDD.docx` (Design / Integration Document; original DOCX, about 106 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF038A_LimrCdng_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

LimrCdng

July 22, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	LimrCdng High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of LimrCdng	5

2.2	Data Flow Diagram	5

2.2.1	Component level DFD	5

2.2.2	Function level DFD	5

3	Constant Data Dictionary	6

3.1	Program (fixed) Constants	6

3.1.1	Embedded Constants	6

4	Software Component Implementation	7

4.1.1	Sub-Module Functions	7

4.1.2	Interrupt Service Routines	7

4.1.3	Server Runnable Functions	7

4.1.4	Module Internal (Local) Functions	7

4.1.5	Transition Functions	7

5	Known Limitations with Design	8

6	UNIT TEST CONSIDERATION	9

Appendix A	Abbreviations and Acronyms	10

Appendix B	Glossary	11

Appendix C	References	12

LimrCdng High-Level Description

This function provides a layer of protection from erroneous signals feeding into SF04 Sum & Limit. It is applied primarily to limiting signals that serve to reduce motor torque command under certain operating conditions. This function can prevent step response or toggling behavior that might cause undesirable vehicle feel. It includes fault injection capability at some inputs to facilitate tuning.

Design details of software module

Refer FDD

Graphical representation of LimrCdng

Data Flow Diagram

Refer FDD

Component level DFD

N/A

Function level DFD

N/A

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer .m file

Software Component Implementation

Sub-Module Functions

Initialization sub-module {_Init()}

  None

Periodic sub-module {LimrCdngPer1}

 Refer FDD

Interrupt Service Routines

None

Server Runnable Functions

None	

Module Internal (Local) Functions

None

Transition Functions

None

Known Limitations with Design

None

UNIT TEST CONSIDERATION

None

Abbreviations and Acronyms

Glossary

Note: Terms and definitions from the source “Nexteer Automotive” take precedence over all other definitions of the same term.  Terms and definitions from the source “Nexteer Automotive” are formulated from multiple sources, including the following:

ISO 9000

ISO/IEC 12207

ISO/IEC 15504

Automotive SPICE® Process Reference Model (PRM)

Automotive SPICE® Process Assessment Model (PAM)

ISO/IEC 15288

ISO 26262

IEEE Standards

SWEBOK

PMBOK

Existing Nexteer Automotive documentation

References

Description | Author | Version | Date
Initial Version | N. Saxton | 1.0.0 | 22-Jul-2015
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
Ref. # | Title | Version
1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2
2 | MDD Guideline | EA4 01.00.00
3 | Software Naming Conventions.doc | 2.0
4 | Software Design and Coding Standards.doc | 2.1
5 | SF038A LimrCdng FDD | See Synergy subproject version
