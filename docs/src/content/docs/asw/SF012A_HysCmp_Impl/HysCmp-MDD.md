---
title: "Hysteresis Compensation — HysCmp MDD"
description: "Converted Design / Integration Document from HysCmp_MDD.docx (DOCX, 114 KB)."
---

:::note
Converted from `SF012A_HysCmp_Impl/doc/HysCmp_MDD.docx` (Design / Integration Document; original DOCX, about 114 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to SF012A_HysCmp_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

 HysCmp

Aug 4, 2015

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Spandana Balani,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	HysCmp & High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of HysCmp	7

3.2	Data Flow Diagram	8

3.2.1	Component level DFD	8

3.2.2	Function level DFD	8

4	Constant Data Dictionary	9

4.1	Program (fixed) Constants	9

4.1.1	Embedded Constants	9

5	Software Component Implementation	10

5.1	Sub-Module Functions	10

5.1.1	Init: HysCmpInit1	10

5.1.2	Per: HysCmpPer1	10

5.2	Server Runables	10

5.3	Interrupt Functions	10

5.4	Module Internal (Local) Functions	10

5.4.1	Local Function #1	10

5.4.1.1	Design Rationale	10

5.4.1.2	Processing	10

5.4.2	Local Function #1	10

5.4.2.1	Design Rationale	10

5.4.2.2	Processing	11

5.4.3	Local Function #1	11

5.4.3.1	Design Rationale	11

5.4.3.2	Processing	11

5.5	GLOBAL Function/Macro Definitions	11

6	Known Limitations with Design	12

7	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

Introduction

Purpose

Scope

 HysCmp & High-Level Description

Refer FDD

Design details of software module

Refer FDD

Graphical representation of HysCmp

Data Flow Diagram

Refer FDD

Component level DFD

Refer FDD

Function level DFD

Refer FDD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Software Component Implementation

Refer FDD

Sub-Module Functions

Init: HysCmpInit1

Refer FDD

Per: HysCmpPer1

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Design Rationale

None

Processing

Refer ‘MoreCmp’ block in Simulink model 

Local Function #1

Design Rationale

None

Processing

Refer ‘LessCmp’ block in Simulink model 

Local Function #1

Design Rationale

None

Processing

Refer ‘CalcAvlCmp’ block in Simulink model 

GLOBAL Function/Macro Definitions

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
Initial Version | SB | 1.0 | 04-Aug-2015
Constant Name | Resolution | Units | Value
Refer .m file |  |  | 
Function Name | MoreCmp | Type | Min | Max
Arguments Passed | TqChg_HwNwtMtr_T_f32 | Float32 | 0 | 20
 | *RiseXPtr_HwNwtMtr_T_f32 | Float32 | 0 | 1
 | *RiseXFac_HwNwtMtr_T_f32 | Float32 | 0 | 1
Return Value | RiseY_Uls_T_f32 | Float32 | 0 | 1
Function Name | LessCmp | Type | Min | Max
Arguments Passed | TqChg_HwNwtMtr_T_f32 | Float32 | 0 | 20
 | *RiseYPtr_Uls_T_f32 | Float32 | 0 | 1
 | *RiseXFac_HwNwtMtr_T_f32 | Float32 | 0 | 1
Return Value | RiseY_Uls_T_f32 | Float32 | 0 | 1
