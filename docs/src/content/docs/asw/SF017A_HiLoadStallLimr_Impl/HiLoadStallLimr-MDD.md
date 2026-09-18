---
title: "High Load Stall Limiter — HiLoadStallLimr MDD"
description: "Converted Design / Integration Document from HiLoadStallLimr_MDD.docx (DOCX, 104 KB)."
---

:::note
Converted from `SF017A_HiLoadStallLimr_Impl/doc/HiLoadStallLimr_MDD.docx` (Design / Integration Document; original DOCX, about 104 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF017A_HiLoadStallLimr_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

HiLoadStallLimr

August 19, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Krishna Kanth Anne,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

2	HiLoadStallLimr & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HiLoadStallLimr	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: HiLoadStallLimrInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: HiLoadStallLimrPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.5	GLOBAL Function/Macro Definitions	10

5.5.1	GLOBAL Function #1	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

MDD for HiLoadStallLimr 

HiLoadStallLimr & High-Level Description

Please refer FDD.

Design details of software module

Graphical representation of HiLoadStallLimr

Data Flow Diagram

Please refer FDD.

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Sub-Module Functions

None

Init: HiLoadStallLimrInit1

Design Rationale

Module Outputs

None

Per: HiLoadStallLimrPer1

Design Rationale

None

Store Module Inputs to Local copies

Please refer FDD

(Processing of function)………

Please refer FDD

Store Local copy of outputs into Module Outputs

Please refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

GLOBAL Function/Macro Definitions

GLOBAL Function #1

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
Initial Version | Krishna Kanth Anne | EA4 01.00.01 | 19-Aug-2015
Constant Name | Resolution | Units | Value
Please refer .m file |  |  | 
Function Name | None | Type | Min | Max
Arguments Passed | None | NA | NA | NA
 | None | NA | NA | NA
Return Value | NA | NA | NA | NA
Function Name | NA | Type | Min | Max
Arguments Passed | None |  |  | 
 | NA |  |  | 
Return Value | NA |  |  | 
