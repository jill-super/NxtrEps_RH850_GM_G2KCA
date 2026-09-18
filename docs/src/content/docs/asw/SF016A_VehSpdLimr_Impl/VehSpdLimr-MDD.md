---
title: "Vehicle Speed Limiter — VehSpdLimr MDD"
description: "Converted Design / Integration Document from VehSpdLimr_MDD.docx (DOCX, 98 KB)."
---

:::note
Converted from `SF016A_VehSpdLimr_Impl/doc/VehSpdLimr_MDD.docx` (Design / Integration Document; original DOCX, about 98 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF016A_VehSpdLimr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

VehSpdLimr

August 10, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Sarika Natu ,

KPIT Technologies,

IndiaChange History

Table of Contents

1	VehSpdLimr High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of VehSpdLimr	5

2.2	Data Flow Diagram	5

2.2.1	Component level DFD	5

2.2.2	Function level DFD	5

3	Constant Data Dictionary	6

3.1	Program (fixed) Constants	6

3.1.1	Embedded Constants	6

4	Software Component Implementation	7

4.1	Sub-Module Functions	7

4.1.1	Init: VehSpdLimr_Init	7

4.1.1.1	Design Rationale	7

4.1.1.2	Module Outputs	7

4.1.2	Per: VehSpdLimr_Per1	7

4.1.2.1	Design Rationale	7

4.1.2.2	Store Module Inputs to Local copies	7

4.1.2.3	(Processing of function)………	7

4.1.2.4	Store Local copy of outputs into Module Outputs	7

4.2	Server Runables	7

4.3	Interrupt Functions	7

4.4	Module Internal (Local) Functions	7

4.5	GLOBAL Function/Macro Definitions	7

5	Known Limitations with Design	8

6	UNIT TEST CONSIDERATION	9

Appendix A	Abbreviations and Acronyms	10

Appendix B	Glossary	11

Appendix C	References	12

VehSpdLimr High-Level Description

The Vehicle Speed Limiting Function determines a limited assist torque command value as a function of vehicle speed and handwheel position to manage mechanical fatigue near end-of-travel positions.

Design details of software module

Graphical representation of VehSpdLimr

Data Flow Diagram

See FDD.

Component level DFD

See FDD.

Function level DFD

See FDD.

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

NA

Software Component Implementation

Sub-Module Functions

Init<Component Name>_Init<n>

Design Rationale

None

Module Outputs

None

Per: VehSpdLimrPer1

Design Rationale

FDD model contains a block named VehSpdLimrPer1

Store Module Inputs to Local copies

See FDD

(Processing of function)………

See FDD

Store Local copy of outputs into Module Outputs

See FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

None

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

Referring to anomaly EA4#1276, following are the discrepancies found:

1) Min/max values of HwAgEotCw, HwAgEotCcw, VehSpdLimrPosMaxOffs1, and VehSpdLimrPosMaxOffs2 need to be set to more realistic values; With the current ranges, there is a possiblity of converting negative numbers to unsigned data types.  Note these ranges need to be coordinated with SF011A and SF018A.  

2) Table VehSpdLimrMaxAssiY monotony needs to be identified as "Decreasing" ­­ the implementation assumes that VehSpdLimrMaxAssiY[0] is the maximum value of the table. 

3) The concatenate block that creates the Y table for the linear interpolation block has the two inputs reversed ­­ the first input to the concatenation should be the max value of the VehSpdLimrMaxAssiY table, and the second input to the concatenation should be the output of the 1­D Lookup block.

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
Initial Version | Sarika Natu(KPIT Technologies) | 1.0 | 10-Aug-2015
Abbreviation or Acronym | Description
 | 
 | 
Term | Definition | Source
MDD | Module Design Document | 
DFD | Data Flow Diagram | 
Ref. # | Title | Version
1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2
2 | MDD Guideline | EA4 01.00.00
3 | EA4 Software Naming Conventions.doc | 01.00.00
4 | Software Design and Coding Standards.doc | 2.1
5 | SF016A_VehSpdLimr_Design | See Synergy subproject version
 |  | 
