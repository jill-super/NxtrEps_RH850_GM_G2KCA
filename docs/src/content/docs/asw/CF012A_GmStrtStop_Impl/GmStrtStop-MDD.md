---
title: "General Motors Start Stop — GmStrtStop MDD"
description: "Converted Design / Integration Document from GmStrtStop_MDD.docx (DOCX, 139 KB)."
---

:::note
Converted from `CF012A_GmStrtStop_Impl/doc/GmStrtStop_MDD.docx` (Design / Integration Document; original DOCX, about 139 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF012A_GmStrtStop_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmStrtStop

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	GmStrtStop High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of GmStrtStop	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: None	9

5.1.2	Per: GmStrtStopPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.4.1.1	Description	9

5.4.2	Local Function #2	9

5.4.2.1	Description	10

5.4.3	Local Function #3	10

5.4.3.1	Description	10

5.4.4	Local Function #4	10

5.4.4.1	Description	10

5.4.5	Local Function #5	11

5.4.5.1	Description	11

5.4.6	Local Function #6	11

5.4.6.1	Description	11

5.4.6.2	Design Rationale	11

5.5	GLOBAL Function/Macro Definitions	11

6	Known Limitations with Design	13

7	UNIT TEST CONSIDERATION	14

Appendix A	Abbreviations and Acronyms	15

Appendix B	Glossary	16

Appendix C	References	17

Introduction

Purpose

Scope

GmStrtStop High-Level Description

Refer to FDD

Design details of software module

Graphical representation of GmStrtStop

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Refer .m file

Software Component Implementation

Sub-Module Functions

Init: None

Per: GmStrtStopPer1

Design Rationale

Refer FDD for the overall functionality. 

Store Module Inputs to Local copies

Refer FDD

(Processing of function)………

Refer FDD

Store Local copy of outputs into Module Outputs

Refer FDD

Server Runables 

None

Interrupt Functions

None

Module Internal (Local) Functions

Local Function #1

Description

 Determination of '' for different mode transitions.

Local Function #2

Description

 This function validates conditions for all state transitions from 'Normal mode'. ‘*’ and ‘*’ are outputs of this function. 

Local Function #3

Description

 This function validates conditions for all state transitions from ‘Intermediate 1 mode’. 

‘*’ and ‘*’ are outputs of this function. 

Local Function #4

Description

 This function validates conditions for all state transitions from ‘Stop mode’. ‘*’ and ‘*’ are outputs of this function.

Local Function #5

Description

 This function validates conditions for all state transitions from 'Intermediate 2 mode'. 

‘*’ and ‘*’ are outputs of this function. 

Local Function #6

Description

This function determines whether exit conditions for states Mod1 and Mod2 have been valid for a long enough period of time.

Design Rationale

This function was created to avoid duplicate code and lower static path count and cyclomatic complexity.

GLOBAL Function/Macro Definitions

None

Known Limitations with Design

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
Initial Version | Sankardu Varadapureddi | 1 | 1-Oct-2015
Added local function GetTmrElpsdThd | Nick Saxton | 2 | 4-Feb-2016
 |  |  | 
Function Name | DtrmnRateLim | Type | Min | Min | Max
Arguments Passed | ActSt_Cnt_T_u08 | uint8 | 0 | 5 | 5
 |  | uint8 | 0 | 5 | 5
Return Value |  | float32 | 0 | 5 | 5
Function Name | NormModExitCdnsChk | Type | Min | Min | Max
Arguments Passed | EngSpd_Rpm_T_f32 | float32 | 0 | 5110 | 5110
 | VehSpd_Kph_T_f32 | float32 | 0 | 511 | 511
 | * | uint8 | 0 | 5 | 5
 | * | float32 | 0 | 1 | 1
Return Value | None |  |  |  | 
Function Name | Inter1ModExitCdnsChk | Type | Min | Min | Max
Arguments Passed | EngSpd_Rpm_T_f32 | float32 | 0 | 5110 | 5110
 | VehSpd_Kph_T_f32 | float32 | 0 | 511 | 511
 | HwVel_HwRadPerSec_T_f32 | float32 | -42 | 42 | 42
 | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10 | 10
 | ToStopModFlg_T_logl | boolean | FALSE | TRUE | TRUE
 | * | uint8 | 0 | 5 | 5
 | * | float32 | 0 | 1 | 1
Return Value | None |  |  |  | 
