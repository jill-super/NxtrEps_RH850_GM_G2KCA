---
title: "Nexteer Detection Library — NxtrDet Module Design Document"
description: "Converted Design / Integration Document from NxtrDet Module Design Document.docx (DOCX, 89 KB)."
---

:::note
Converted from `AR998A_NxtrDet_Impl/doc/NxtrDet Module Design Document.docx` (Design / Integration Document; original DOCX, about 89 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to AR998A_NxtrDet_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

NxtrDet

Oct 6, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Software Group,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	NxtrDet High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of NxtrDet	6

3.2	Data Flow Diagram	6

3.2.1	Component level DFD	6

3.2.2	Function level DFD	6

4	Constant Data Dictionary	7

4.1	Program (fixed) Constants	7

4.1.1	Embedded Constants	7

5	Software Component Implementation	8

5.1	Sub-Module Functions	8

5.1.1	Init: NxtrDet	8

5.1.2	Per: NxtrDet	8

5.2	Server Runables	8

5.3	Interrupt Functions	8

5.4	Module Internal (Local) Functions	8

5.4.1	Local Function #1	8

5.4.1.1	Design Rationale	8

5.4.1.2	Processing	8

5.5	GLOBAL Function/Macro Definitions	8

5.5.1	GLOBAL Function #1	8

5.5.1.1	Design Rationale	8

5.5.1.2	Processing	8

6	Known Limitations with Design	10

7	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

Introduction

Purpose

Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance. 

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.  

May: indicates an optional action.

NxtrDet High-Level Description

See FDD

Design details of software module

Graphical representation of NxtrDet

None

Data Flow Diagram

Component level DFD

N/A

Function level DFD

N/A

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Constants containing the Nexteer ModuleIDs defined for Det functionality are defined in the .m file included in the doc folder of this component.  This is to allow new SWCs adding new Det errors to not drive changes to the design project, only to the implementation project.

Local Constants

Software Component Implementation

Sub-Module Functions

Init: NxtrDet

None

Per: NxtrDet

None

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

Processing

GLOBAL Function/Macro Definitions

GLOBAL Function #1

Design Rationale

Processing

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
Initial Version | Lucas Wendling | 1 | 10/06/15
Constant Name | Resolution | Units | Value
None |  |  | 
Function Name | (Exact name used) | Type | Min | Max
Arguments Passed | None | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]>
 |  |  |  | 
Return Value |  |  |  | 
Function Name | (Exact name used) | Type | Min | Max
Arguments Passed | None | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]> | <Refer MDD guidelines[1]>
 |  |  |  | 
Return Value |  |  |  | 
