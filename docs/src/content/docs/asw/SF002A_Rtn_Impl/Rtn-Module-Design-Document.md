---
title: "Return — Rtn Module Design Document"
description: "Converted Design / Integration Document from Rtn_Module Design Document.docx (DOCX, 112 KB)."
---

:::note
Converted from `SF002A_Rtn_Impl/doc/Rtn_Module Design Document.docx` (Design / Integration Document; original DOCX, about 112 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF002A_Rtn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

Return

June 30, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Spandana BalaniChange History

Table of Contents

1	Introduction	3

1.1	Purpose	3

1.2	Scope	3

2	<Component Name> & High-Level Description	3

3	Design details of software module	3

3.1	Graphical representation of <Component Name>	3

3.2	Data Flow Diagram	3

3.2.1	Component level DFD	3

3.2.2	Function level DFD	3

4	Constant Data Dictionary	3

4.1	Program (fixed) Constants	3

4.1.1	Embedded Constants	3

5	Software Component Implementation	3

5.1.1	Sub-Module Functions	3

5.1.2	Interrupt Service Routines	3

5.1.3	Server Runnable Functions	3

5.1.4	Module Internal (Local) Functions	3

5.1.5	Transition Functions	3

6	Known Limitations with Design	3

7	UNIT TEST CONSIDERATION	3

Appendix A	Abbreviations and Acronyms	3

Appendix B	Glossary	3

Appendix C	References	3

Introduction

Purpose

Scope

Rtn High-Level Description

Refer to FDD

Design details of software module

Graphical representation of Rtn

Data Flow Diagram

Component level DFD

Refer to FDD

Function level DFD

Refer to FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

None

Software Component Implementation

Sub-Module Functions

Initialization sub-module {_Init()}

  None

Periodic sub-module RtnPer1

Design Rationale - Fault Injection client call is conditional compiled based on “FLTINJENA” build constant.

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

Description | Author | Version | Date | 
Initial Version | SB | 1 | 30-Jun-2015 | 
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
Ref. # | Title | Version
1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2
2 | MDD Guideline | EA4 01.00.00
3 | Software Naming Conventions.doc | 2.0
4 | Software Design and Coding Standards.doc | 2.1
5 | FDD – SF002A_Rtn_Design | See Synergy Sub project version
