---
title: "General Motors Torque Arbitration — GmTqArbn MDD"
description: "Converted Design / Integration Document from GmTqArbn_MDD.docx (DOCX, 129 KB)."
---

:::note
Converted from `CF010A_GmTqArbn_Impl/doc/GmTqArbn_MDD.docx` (Design / Integration Document; original DOCX, about 129 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to CF010A_GmTqArbn_Impl](./)

*Conversion method: automatic text extraction from the Word document.*

For

GmTqArbn

, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By: 

Nick Saxton,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	5

1.1	Purpose	5

1.2	Scope	5

2	GmTqArbn High-Level Description	6

3	Design details of software module	7

3.1	Graphical representation of GmTqArbn	7

3.2	Data Flow Diagram	7

3.2.1	Component level DFD	7

3.2.2	Function level DFD	7

4	Constant Data Dictionary	8

4.1	Program (fixed) Constants	8

4.1.1	Embedded Constants	8

5	Software Component Implementation	9

5.1	Sub-Module Functions	9

5.1.1	Init: GmTqArbnInit1	9

5.1.1.1	Design Rationale	9

5.1.1.2	Module Outputs	9

5.1.2	Per: GmTqArbnPer1	9

5.1.2.1	Design Rationale	9

5.1.2.2	Store Module Inputs to Local copies	9

5.1.2.3	(Processing of function)………	9

5.1.2.4	Store Local copy of outputs into Module Outputs	9

5.2	Server Runables	9

5.3	Interrupt Functions	9

5.4	Module Internal (Local) Functions	9

5.4.1	Local Function #1	9

5.4.1.1	Description	10

5.4.2	Local Function #2	10

5.4.2.1	Description	10

5.4.3	Local Function #3	10

5.4.3.1	Description	10

5.5	GLOBAL Function/Macro Definitions	10

6	Known Limitations with Design	11

7	UNIT TEST CONSIDERATION	12

Appendix A	Abbreviations and Acronyms	13

Appendix B	Glossary	14

Appendix C	References	15

Introduction

Purpose

Scope

GmTqArbn High-Level Description

Refer to FDD

Design details of software module

Graphical representation of GmTqArbn

Data Flow Diagram

Refer FDD

Component level DFD

Function level DFD

Constant Data Dictionary

Program (fixed) Constants

Embedded Constants

Local Constants

Refer .m file 

Software Component Implementation

Sub-Module Functions

Init: GmTqArbnInit1

Design Rationale

Refer FDD 

Module Outputs

Refer FDD

Per: GmTqArbnPer1

Design Rationale

Refer FDD

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

 'PosnServo_Smoothed_Ramp'  functional block implementation.

Local Function #2

Description

 'Ramp to Value' functional block implementation. 

Local Function #3

Description

 'ESC Logic' functional block implementation. 

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
Initial Version | Sankardu Varadapureddi | 1 | 5-Oct-2015
Updated graphical representation to match anomaly EA4#2143 fixes | Nick Saxton | 2 | 1-Feb-2016
 |  |  | 
Function Name | PosnServoSmotRamp | Type | Min | Min | Max
Arguments Passed | PosSrvoCmd_HwNwtMtr_T_f32 | float32 | -8.8 | 8.8 | 8.8
 | PosSrvoSmoothEnable_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
 | HwTq_HwNwtMtr_T_f32 | float32 | -10 | 10 | 10
 | *APAOvrlCmd_HwNwtMtr_T_f32 | float32 | -8.8 | 8.8 | 8.8
 | *ScaleFactor_Uls_T_f32 | float32 | 0 | 1 | 1
Return Value | none |  |  |  | 
Function Name | RampVal | Type | Min | Min | Max
Arguments Passed | DesLKATqCmd_HwNwtMtr_T_f32 | float32 | -3 | 3 | 3
 | VehSpd_Kph_T_f32 | float32 | 0 | 511 | 511
Return Value | LKAInterTqCmd_HwNwtMtr_T_f32 | float32 | -3 | 3 | 3
Function Name | ESCLogic | Type | Min | Min | Max
Arguments Passed | EscCmd_HwNwtMtr_T_f32 | float32 | -10 | 10 | 10
 | EscSt_Cnt_T_u08 | uint8 | 0 | 4 | 4
 | *ESCTqCmd_HwNwtMtr_T_f32 | float32 | -3 | 3 | 3
 | *EscLimdActv_Cnt_T_logl | boolean | FALSE | TRUE | TRUE
Return Value | None |  |  |  | 
